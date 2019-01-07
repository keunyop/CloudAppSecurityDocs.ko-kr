---
title: ICAP를 통한 Cloud App Security 외부 DLP 통합
description: 이 문서에서는 Cloud App Security 및 stunnel 설정에서 ICAP 연결을 구성하는 데 필요한 단계를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9656f6c6-7dd4-4c4c-a0eb-f22afce78071
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 86ef20ca985213a369035505232d4bf594a47caf
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53177235"
---
# <a name="external-dlp-integration"></a>외부 DLP 통합

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security는 기존 DLP 솔루션과 통합되어 온-프레미스 및 클라우드 활동에서 일관된 통합 정책을 유지하면서 이러한 컨트롤을 클라우드로 확장할 수 있습니다. 플랫폼에서는 REST API 및 ICAP를 포함한 간편한 인터페이스를 내보내 Symantec 데이터 손실 방지(이전 Vontu 데이터 손실 방지) 또는 Forcepoint DLP와 같은 콘텐츠 분류 시스템과의 통합을 구현합니다. 

[RFC 3507](https://tools.ietf.org/html/rfc3507)에 설명된 HTTP와 유사한 프로토콜인 표준 ICAP 프로토콜을 사용하여 통합을 수행합니다. 데이터 전송을 위한 ICAP를 보호하려면 DLP 솔루션과 Cloud App Security 간에 보안 SSL 터널(stunnel)을 설정해야 합니다. stunnel 설정은 DLP 서버와 Cloud App Security 간에 이동할 때 데이터에 대한 TLS 암호화 기능을 제공합니다. 

이 가이드에서는 ICAP 연결을 통해 통신을 보호하기 위해 Cloud App Security 및 stunnel 설정에서 ICAP 연결을 구성하는 데 필요한 단계를 제공합니다.


## <a name="architecture"></a>아키텍처
Cloud App Security는 클라우드 환경을 검색하고 파일 정책 구성에 따라 내부 DLP 엔진 또는 외부 DLP를 사용하여 파일을 검색할지 여부를 결정합니다. 외부 DLP 검색이 적용되면 파일은 DLP verdict: allowed/blocked를 위해 ICAP 어플라이언스에 릴레이되는 경우 보안 터널을 통해 고객 환경에 전송됩니다. 응답은 알림, 격리 및 공유 컨트롤과 같은 후속 작업을 결정하기 위해 정책에서 사용되는 경우 stunnel을 통해 다시 Cloud App Security에 전송됩니다.

![Stunnel 아키텍처](./media/icap-architecture-stunnel.png)

Cloud App Security는 Azure에서 실행되므로 Azure에 배포하면 성능이 향상됩니다. 그러나 기타 클라우드 및 온-프레미스 배포를 포함한 기타 옵션이 지원됩니다. 다른 환경에 배포하면 대기 시간이 길어지고 처리량이 감소하므로 성능이 저하됩니다. 트래픽이 암호화되도록 하려면 ICAP 서버 및 stunnel을 함께 동일한 네트워크에 배포해야 합니다.

## <a name="prerequisites"></a>필수 구성 요소
Cloud App Security에서 stunnel을 통해 데이터를 ICAP 서버에 전송하려면 동적 소스 포트 번호를 통해 Cloud App Security에서 사용되는 외부 IP 주소로 DMZ 방화벽을 엽니다. 

1.  원본 주소: [필수 구성 요소에 따라 앱 연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#prerequisites) 참조
2.  원본 TCP 포트: 동적
3.  대상 주소: 다음 단계에서 구성할 외부 ICAP 서버에 연결된 stunnel의 하나 또는 두 개의 IP 주소
4.  대상 TCP 포트: 네트워크에서 정의된 대로

> [!NOTE] 
> 기본적으로 stunnel 포트 번호는 11344로 설정됩니다. 필요한 경우 다른 포트로 변경할 수 있지만 새 포트 번호를 기록해 두어야 합니다. 다음 단계에서 해당 포트 번호를 입력해야 합니다.

## <a name="step-1--set-up-icap-server"></a>1단계:  ICAP 서버 설정

ICAP 서버를 설정하여 포트 번호를 적어 두고 **모드**를 **차단**으로 설정했는지 확인합니다. 차단 모드는 분류 verdict를 다시 Cloud App Security로 릴레이하도록 ICAP 서버를 설정합니다.

이 설치를 수행하는 방법에 대한 지침은 외부 DLP 제품 설명서를 참조하세요. 예를 들어 [부록 A: Forcepoint ICAP 서버 설정](#forcepoint) 및 [부록 B: Symantec 배포 가이드](#symantec)를 참조하세요.

## <a name="step-2--set-up-your-stunnel-server"></a>2단계:  stunnel 서버 설정 

이 단계에서 ICAP 서버에 연결된 stunnel을 설정합니다. 

>[!NOTE]
> 이 단계는 적극 권장되지만 선택 사항이므로 테스트 워크로드에서 건너뛸 수 있습니다. 

### <a name="install-stunnel-on-a-server"></a>서버에 stunnel 설치

**필수 구성 요소**

- **서버** - 주요 배포에 따라 Windows Server 또는 Linux 서버.

stunnel 설치를 지원하는 서버 유형에 대한 자세한 내용은 [stunnel 웹 사이트](https://www.stunnel.org/index.html)를 참조하세요. Linux를 사용 중이면 Linux 배포 관리자를 사용하여 설치할 수 있습니다.

#### <a name="install-stunnel-on-windows"></a>Windows에 stunnel 설치

1. [최신 Windows Server 설치를 다운로드합니다](https://www.stunnel.org/downloads.html)(이 애플리케이션은 최근 Windows Server 버전에서 작업해야 함).
   (기본 설치)

2. 설치하는 동안 새로운 자체 서명된 인증서를 만들지 마세요. 이후 단계에서 인증서를 만듭니다.

3. **Start server after installation**(설치한 후 서버 시작)을 클릭합니다.

4. 다음 방법 중 하나로 인증서를 만듭니다.

   - 인증서 관리 서버를 사용하여 ICAP 서버에 SSL 인증서를 만듭니다. 그런 다음, stunnel 설치를 위해 준비한 서버에 키를 복사합니다.
   - 또는 stunnel 서버에서 다음 OpenSSL 명령을 사용하여 개인 키 및 자체 서명된 인증서를 생성합니다. 다음 변수를 바꿉니다.
     - **key.pem**(개인 키 이름 포함)
     - **cert.pem**(인증서 이름 포함)
     - **stunnel-key**(새로 만들어진 키 이름 포함)

5. stunnel 설치 경로에서 config 디렉터리를 엽니다. 기본 경로는 c:\Program Files (x86)\stunnel\config\입니다.
6. 관리자 권한으로 명령줄을 실행합니다. `..\bin\openssl.exe genrsa -out key.pem 2048 `
      
     ` ..\bin\openssl.exe  req -new -x509 -config ".\openssl.cnf" -key key.pem -out .\cert.pem -days 1095`

7. cert.pem 및 key.pem을 연결하고 파일에 저장합니다. `type cert.pem key.pem >> stunnel-key.pem`

8. [공개 키를 다운로드](https://adaprodconsole.blob.core.windows.net/icap/publicCert.pem)하고 **C:\Program Files (x86)\stunnel\config\MCASca.pem** 위치에 저장합니다.

9. 다음 규칙을 추가하여 Windows 방화벽에서 포트를 엽니다.

       rem Open TCP Port 11344 inbound and outbound
       netsh advfirewall firewall add rule name="Secure ICAP TCP Port 11344" dir=in action=allow protocol=TCP localport=11344
       netsh advfirewall firewall add rule name="Secure ICAP TCP Port 11344" dir=out action=allow protocol=TCP localport=11344

10. `c:\Program Files (x86)\stunnel\bin\stunnel.exe`를 실행하여 stunnel 애플리케이션을 엽니다. 

11. **구성**, **구성 편집**을 차례로 클릭합니다.

    ![Windows Server 구성 편집](./media/stunnel-windows.png)
 
12. 파일을 열고 다음 서버 구성 줄을 붙여넣습니다. **DLP Server IP**는 ICAP 서버의 IP 주소이고, **stunnel-key**는 이전 단계에서 만든 키이고, **MCASCAfile**은 Cloud App Security stunnel 클라이언트의 공용 인증서입니다. 배치된 예제 텍스트를 모두 삭제하고(예제에서는 Gmail 텍스트를 표시함) 다음 텍스트를 파일에 복사합니다.

        [microsoft-Cloud App Security]
        accept = 0.0.0.0:11344
        connect = **ICAP Server IP**:1344
        cert = C:\Program Files (x86)\stunnel\config\**stunnel-key**.pem
        CAfile = C:\Program Files (x86)\stunnel\config\**MCASCAfile**.pem
        TIMEOUTclose = 0
        client = no
13. 파일을 저장하고 **구성 다시 로드**를 클릭합니다.

14. 모든 것이 예상대로 실행 중인지 유효성을 검사하려면 명령 프롬프트에서 `netstat -nao  | findstr 11344`를 실행합니다.
 

#### <a name="install-stunnel-on-ubuntu"></a>Ubuntu에 stunnel 설치

다른 서버 사용 병렬 명령에 대해 루트 사용자로 서명된 경우 다음 예제는 Ubuntu 서버 설치를 기반으로 합니다. 

준비된 서버에서 최신 버전의 stunnel을 다운로드하여 설치합니다. stunnel 및 OpenSSL을 둘 다 설치하려면 Ubuntu 서버에서 다음 명령을 실행합니다.

    apt-get update
    apt-get install openssl -y
    apt-get install stunnel4 -y

콘솔에서 다음 명령을 실행하여 stunnel이 설치되는지 확인합니다. 버전 번호 및 구성 옵션 목록을 확인해야 합니다.

    stunnel-version

### <a name="generate-certificates"></a>인증서 생성

ICAP 서버 및 Cloud App Security에서는 stunnel을 통해 서버 암호화 및 인증에 개인 키 및 공용 인증서를 사용합니다. stunnel이 백그라운드 서비스로 실행될 수 있도록 암호 없이 개인 키를 만들어야 합니다. 또한 파일에 대한 사용 권한을 **읽기 가능**(stunnel 소유자의 경우) 및 **없음**(다른 모든 사용자의 경우)으로 설정합니다.

다음 방법 중 하나로 인증서를 만들 수 있습니다.
- 인증서 관리 서버를 사용하여 ICAP 서버에 SSL 인증서를 만듭니다. 그런 다음, stunnel 설치를 위해 준비한 서버에 키를 복사합니다. 
- 또는 stunnel 서버에서 다음 OpenSSL 명령을 사용하여 개인 키 및 자체 서명된 인증서를 생성합니다. 다음 변수를 바꿉니다.
    - **“key.pem”**(개인 키 이름 포함)
    - **“cert.pem”**(인증서 이름 포함)
    - **“stunnel-key”**(새로 만들어진 키 이름 포함)
       
            openssl genrsa -out key.pem 2048
            openssl req -new -x509 -key key.pem -out cert.pem -days 1095
            cat key.pem cert.pem >> /etc/ssl/private/stunnel-key.pem

### <a name="download-the-cloud-app-security-stunnel-client-public-key"></a>Cloud App Security stunnel 클라이언트 공개 키 다운로드

이 위치(https://adaprodconsole.blob.core.windows.net/icap/publicCert.pem)에서 공개 키를 다운로드하고 이 위치(**/etc/ssl/certs/MCASCAfile.pem**)에 저장

### <a name="configure-stunnel"></a>stunnel 구성 

stunnel 구성은 stunnel.conf 파일에서 설정됩니다.

1. **vim /etc/stunnel/stunnel.conf** 디렉터리에서 stunnel.conf 파일을 만듭니다.

2. 파일을 열고 다음 서버 구성 줄을 붙여넣습니다.  **DLP Server IP**는 ICAP 서버의 IP 주소이고, **stunnel-key**는 이전 단계에서 만든 키이고, **MCASCAfile**은 Cloud App Security stunnel 클라이언트의 공용 인증서입니다.

        [microsoft-Cloud App Security]
        accept = 0.0.0.0:11344
        connect = **ICAP Server IP**:1344
        cert = /etc/ssl/private/**stunnel-key**.pem
        CAfile = /etc/ssl/certs/**MCASCAfile**.pem
        TIMEOUTclose = 1
        client = no


### <a name="update-your-ip-table"></a>IP 테이블 업데이트
다음 경로 규칙을 사용하여 IP 주소 테이블을 업데이트합니다.
   
    iptables -I INPUT -p tcp --dport 11344 -j ACCEPT

IP 테이블에 대한 업데이트를 영구적으로 설정하려면 다음 명령을 사용합니다.

     sudo apt-get install iptables-persistent
     sudo /sbin/iptables-save > /etc/iptables/rules.v4
 

### <a name="run-stunnel"></a>stunnel 실행
1. stunnel 서버에서 다음 명령을 실행합니다.

        vim /etc/default/stunnel4

2. 변수 ENABLED를 1로 변경합니다.

        ENABLED=1

3. 구성을 적용하려면 서비스를 다시 시작합니다.

        /etc/init.d/stunnel4 restart

4. 다음 명령을 실행하여 stunnel이 제대로 실행 중인지 확인합니다.

        ps -A | grep stunnel

    그리고 나열된 포트를 수신 대기하는지 확인합니다.

        netstat -anp | grep 11344

5. stunnel 서버가 배포된 네트워크가 앞에서 설명한 대로 네트워크 필수 구성 요소와 일치하는지 확인합니다. Cloud App Security에서 들어오는 연결이 서버에 성공적으로 도달되도록 하기 위해 이 작업이 필요합니다.

프로세스가 실행되고 있지 않으면 [stunnel 설명서](https://www.stunnel.org/docs.html)를 참조하여 문제를 해결하세요.


## <a name="step-3--connect-to-cloud-app-security"></a>3단계:  Cloud App Security에 연결

1. Cloud App Security의 **설정**에서 **보안 확장**을 선택하고 **외부 DLP** 탭을 선택합니다.

2. 더하기를 클릭하여 새 연결을 추가합니다. 

3. **Add new external DLP**(새 외부 DLP 추가) 마법사에서 커넥터를 식별하는 데 사용할 **연결 이름**(예: 내 Forcepoint 커넥터)을 제공합니다.

4. **연결 형식**을 선택합니다.
    - **Symantec Vontu** – Vontu DLP 어플라이언스에 사용자 지정 통합을 사용합니다.
    - **Forcepoint DLP** – Forcepoint DLP 어플라이언스에 사용자 지정 통합을 사용합니다.
    - **Generic ICAP – REQMOD** - [요청 수정](https://tools.ietf.org/html/rfc3507)을 사용하는 다른 DLP 어플라이언스를 사용합니다.
    - **Generic ICAP – RESPMOD** - [응답 수정](https://tools.ietf.org/html/rfc3507)을 사용하는 다른 DLP 어플라이언스를 사용합니다.
    ![Cloud App Security ICAP 연결](./media/icap-wizard1.png)

5. 이전 단계에서 생성한 공용 인증서인 “cert.pem”을 찾아서 stunnel에 연결합니다. **다음**을 클릭합니다.

   > [!NOTE]
   > 암호화된 stunnel 게이트웨이를 설정하려면 **Use secure ICAP**(보안 ICAP 사용) 상자를 선택하는 것이 좋습니다. 테스트 목적이거나 stunnel 서버가 없는 경우 이 상자를 선택 취소하여 DLP 서버와 직접 통합할 수 있습니다. 

5. **서버 구성** 화면에서, 2단계에서 설정한 stunnel 서버의 **IP 주소** 및 **포트**를 제공합니다. 부하 분산 목적으로 추가 서버의 **IP 주소** 및 **포트**를 구성할 수 있습니다. 제공된 IP 주소는 서버의 외부 정적 IP 주소여야 합니다.

   ![Cloud App Security ICAP 연결](./media/icap-wizard2.png)
6. **다음**을 클릭합니다. Cloud App Security에서는 구성한 서버에 대한 연결을 테스트합니다. 오류가 표시되면 지침 및 네트워크 설정을 검토합니다. 성공적으로 연결된 후 **끝내기**를 클릭할 수 있습니다.

7. 이제 트래픽을 이 외부 DLP 서버로 전송하려면 **파일 정책**을 만들 때 **콘텐츠 검사 방법**에서 만든 연결을 선택합니다. 자세한 내용은 [파일 정책 만들기](data-protection-policies.md)를 참조하세요.


## 부록 A: ForcePoint ICAP 서버 설정 <a name="forcepoint"></a>

ForcePoint에서 다음 단계를 사용하여 어플라이언스를 설정합니다.

1.  DLP 어플라이언스에서 **배포** > **시스템 모듈**로 이동합니다. 

    ![ICAP 배포](./media/icap-system-modules.png)

2.  **일반** 탭에서 **ICAP 서버**가 **사용**으로 설정되고 기본 **포트**가 **1344**로 설정되어 있는지 확인합니다. 또한 **Allow connection to this ICAP Server from the following IP addresses**(다음 IP 주소에서 이 ICAP 서버에 대한 연결 허용)에서 **모든 IP 주소**를 선택합니다.
 
    ![ICAP 구성](./media/icap-ip-address.png)

3.  [HTTP/HTTPS] 탭에서 **모드**를 **차단**으로 설정해야 합니다.
 
    ![ICAP 차단](./media/icap-blocking.png)
 

## 부록 B: Symantec 배포 가이드 <a name="symantec"></a>

지원되는 Symantec DLP 버전은 11 이상입니다. 

위에서 언급한 대로 Cloud App Security 테넌트가 있는 동일한 Azure 데이터 센터에 검색 서버를 배포해야 합니다. 검색 서버는 전용 IPSec 터널을 통해 적용 서버와 동기화됩니다. 
 
### <a name="detection-server-installation"></a>검색 서버 설치 
Cloud App Security에서 사용하는 검색 서버는 표준 Network Prevent for Web 서버입니다. 여러 구성 옵션을 변경해야 합니다.
1. **평가 모드** 사용 안 함:
   1. **시스템** > **서버 및 탐지기** 아래에서 ICAP 대상을 클릭합니다. 
    
      ![ICAP 대상](./media/icap-target.png)
    
   2. **구성**을 클릭합니다. 
    
      ![ICAP 대상 구성](./media/configure-icap-target.png)
    
   3. **평가 모드**를 사용하지 않도록 구성합니다.
    
      ![평가 모드 사용 안 함](./media/icap-disable-trial-mode.png)
    
2. **ICAP** > **응답 필터링** 아래에서 **다음보다 적은 응답 무시** 값을 1로 변경합니다.


3. "application/\*"을 **콘텐츠 형식 검사</em>** 의 목록에 추가합니다.
     ![콘텐츠 형식 검사](./media/icap-inspect-content-type.png)

4. **저장**을 클릭합니다.


### <a name="policy-configuration"></a>정책 구성
Cloud App Security는 Symantec DLP에 포함된 모든 검색 규칙 형식을 원활하게 지원하므로 기존 규칙을 바꿀 필요가 없습니다. 하지만 전체 통합을 사용하려면 모든 기존 및 새 정책에 적용되어야 하는 구성 변경 내용이 있습니다. 이 변경 내용은 모든 정책에 대한 특정 응답 규칙의 추가입니다. 

Vontu에 구성 변경 내용 추가:

1.  **관리** > **정책** > **응답 규칙**으로 이동해서 **응답 규칙 추가**를 클릭합니다.
    
    ![응답 규칙 추가](./media/icap-add-response-rule.png)

2.  **자동화된 응답**을 선택했는지 확인하고 **다음**을 클릭합니다.

    ![자동화된 응답](./media/icap-automated-response.png)

3. 예를 들어 **Block HTTP/HTTPS**와 같은 규칙 이름을 입력합니다. **작업** 아래에서 **Block HTTP/HTTPS**를 선택하고 **저장**을 클릭합니다.

    ![http 차단](./media/icap-block-http.png)

만든 규칙을 원하는 기존 정책에 추가합니다.

1. 각 정책에서 **응답** 탭으로 전환합니다.

2. **응답 규칙** 드롭다운에서, 앞서 만든 응답 차단 규칙을 선택합니다.

3. 정책을 저장합니다.
   
    ![평가 모드 사용 안 함](./media/icap-add-policy.png)

이 규칙은 모든 기존 정책에 추가되어야 합니다.

>[!NOTE]
> Symantec vontu를 사용하여 Dropbox에서 파일을 검색하는 경우 CAS는 파일을 다음 URL에서 발생한 것으로 자동으로 표시합니다. http://misc/filename 이 자리 표시자 url은 실제로 이동되지 않지만 로깅 용도로 사용됩니다.


## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
