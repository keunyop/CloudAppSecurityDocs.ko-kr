---
title: Windows의 Docker를 사용하여 Cloud App Security의 연속 보고서 롤아웃 | Microsoft Docs
description: 이 문서에서는 온-프레미스 서버에서 Windows의 Docker를 사용하여 Cloud App Security의 연속 보고서에 대해 자동 로그 업로드를 구성하는 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 4/19/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: ff73a393-da43-4954-8b02-38d2a48d39b3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6f97426e1e1c18e2be3adb61ad5b3df95fb2c9c4
ms.sourcegitcommit: b0ae3a969a85a1ae0332a30efd058e415d9efb5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59904280"
---
# <a name="docker-on-windows-on-premises"></a>Windows의 Docker 온-프레미스

*적용 대상: Microsoft Cloud App Security*

Windows의 Docker를 사용하여 Cloud App Security의 연속 보고서용 자동 로그 업로드를 구성할 수 있습니다.

## <a name="technical-requirements"></a>기술 요구 사항

- OS: **Windows 10**(Fall Creators Update) 및 Windows Server **버전 1709+**

- 디스크 공간: 250GB

- CPU: 2

- RAM: 4GB

- [네트워크 요구 사항](network-requirements.md#log-collector)에 설명된 대로 방화벽 설정

- 운영 체제의 가상화가 Hyper-V로 활성화되어 있어야 함

## <a name="log-collector-performance"></a>로그 수집기 성능

로그 수집기는 시간당 최대 50GB의 로그 용량을 성공적으로 처리할 수 있습니다. 로그 수집 프로세스의 주요 병목 상태는 다음과 같습니다.

- 네트워크 대역폭 - 네트워크 대역폭은 로그 업로드 속도를 결정합니다.

- 가상 머신의 I/O 성능 - 로그가 로그 수집기의 디스크에 기록되는 속도를 결정합니다. 로그 수집기에는 로그가 도착하는 속도를 모니터링하고 업로드 속도와 비교하는 기본 제공 보안 메커니즘이 있습니다. 정체가 발생할 경우 로그 수집기에서 로그 파일 삭제를 시작합니다. 설치가 일반적으로 시간당 50GB를 초과할 경우 여러 로그 수집기 간에 트래픽을 분할하는 것이 좋습니다.

## <a name="set-up-and-configuration"></a>설정 및 구성  

### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>1단계 - 웹 포털 구성: 데이터 원본을 정의하고 로그 수집기에 연결

1. **자동 로그 업로드** 설정 페이지로 이동합니다. 

     a. Cloud App Security 포털에서 설정 아이콘, **로그 수집기**를 차례로 클릭합니다.

      ![설정 아이콘](./media/settings-icon.png)

2. 로그를 업로드하려는 각 방화벽 또는 프록시에 대해 일치하는 데이터 원본을 만듭니다.

     a. **데이터 원본 추가**를 클릭합니다.

      ![데이터 원본 추가](./media/add-data-source.png)
          
     b. 프록시 또는 방화벽에 **이름**을 지정합니다.
      
      ![ubuntu1](./media/ubuntu1.png)

     c. **원본** 목록에서 어플라이언스를 선택합니다. 나열되지 않은 네트워크 어플라이언스를 사용하기 위해 **사용자 지정 로그 형식**을 선택하는 경우 구성 지침은 [사용자 지정 로그 파서 작업](custom-log-parser.md)을 참조하세요.

     d. 예상 로그 형식 샘플과 로그를 비교합니다. 로그 파일 형식이 이 샘플과 일치하지 않는 경우 데이터 원본을 **기타**로 추가해야 합니다.

     e. **수신기 유형**을 **FTP**, **FTPS**, **Syslog – UDP** 또는 **Syslog – TCP** 또는 **Syslog – TLS**로 설정합니다.
     
     >[!NOTE]
     >보안 전송 프로토콜(FTPS 및 Syslog - TLS)과 통합하려면 종종 추가 설정 또는 방화벽/프록시가 필요합니다.

      f. 해당 로그를 사용하여 네트워크의 트래픽을 검색할 수 있는 각 방화벽 및 프록시에 대해 이 프로세스를 반복합니다. 네트워크 디바이스당 전용 데이터 원본을 사용할 수 있도록 설정하는 것이 좋습니다.
     - 조사를 위해 각 디바이스의 상태를 개별적으로 모니터링합니다.
     - 각 디바이스를 다른 사용자 세그먼트를 사용하는 경우 디바이스별로 Shadow IT Discovery를 탐색합니다.

3. 맨 위에 있는 **로그 수집기** 탭으로 이동합니다.

   a. **로그 수집기 추가**를 클릭합니다.

   b. 로그 수집기에 **이름**을 지정합니다.

   c. Docker를 배포하는 데 사용할 머신의 **호스트 IP 주소**를 입력합니다. 호스트 이름을 확인할 DNS 서버(또는 이와 동등한)가 있으면 호스트 IP 주소를 컴퓨터 이름으로 바꿀 수 있습니다.

   d. 수집기에 연결할 **데이터 소스**를 모두 선택하고 **업데이트**를 클릭하여 구성을 저장한 후, 다음 배포 단계를 확인합니다.

   ![ubuntu2](./media/ubuntu2.png)

   > [!NOTE]
   > - 단일 로그 수집기로 여러 데이터 원본을 처리할 수 있습니다.
   > - Cloud App Security와 통신하도록 로그 수집기를 구성하는 경우 정보가 필요하므로 화면의 내용을 복사합니다. Syslog를 선택한 경우 이 정보에는 Syslog 수신기가 수신 대기하는 포트에 대한 정보가 포함됩니다.

4. 추가 배포 정보가 표시됩니다. 대화 상자의 실행 명령을 **복사**합니다. 클립보드에 복사 아이콘을 사용할 수 있습니다. ![클립보드 아이콘으로 복사](./media/copy-icon.png) 이 항목이 나중에 필요합니다.

5. 예상 데이터 소스 구성 **내보내기**를 수행합니다. 이 구성에서는 어플라이언스에서 로그 내보내기를 설정하는 방법을 설명합니다.

   ![로그 수집기 만들기](./media/windows7.png)

### <a name="step-2--on-premises-deployment-of-your-machine"></a>2단계 - 컴퓨터 온-프레미스 배포
다음 단계에서는 Windows에서 배포를 설명합니다. 다른 플랫폼의 경우 배포 단계가 약간 다릅니다.

1. Windows 머신에서 관리자 권한으로 PowerShell 터미널을 엽니다.

2. 다음 명령을 사용하여 Windows Docker 설치 관리자를 다운로드합니다.<br>
 `Invoke-WebRequest https://adaprodconsole.blob.core.windows.net/public-files/LogCollectorInstaller.ps1 -OutFile (Join-Path $Env:Temp LogCollectorInstaller.ps1)`
<br>Microsoft에서 서명된 설치 관리자의 유효성을 검사하려는 경우 [설치 관리자 서명 유효성 검사](#validate-signature)를 참조하세요.

3. PowerShell 스크립트를 실행하도록 설정하려면 `Set-ExecutionPolicy RemoteSigned`를 실행합니다.

4. `& (Join-Path $Env:Temp LogCollectorInstaller.ps1)`을 실행합니다.<br>
그러면 머신에 Docker 클라이언트를 설치합니다. 로그 수집기 컨테이너가 설치되는 동안 머신을 두 번 다시 시작하고 다시 로그인해야 합니다. **Docker 클라이언트를 Linux 컨테이너를 사용 하도록 설정 되어 있는지 확인 합니다.**

5. 설치 관리자를 저장한 디렉터리에서 다시 시작할 때마다 `& (Join-Path $Env:Temp LogCollectorInstaller.ps1)`을 다시 실행합니다.<br>  

6. 설치를 완료하기 전에 앞에서 복사한 run 명령에 붙여넣어야 합니다.

7. 수집기 구성을 가져와서 호스팅 컴퓨터에 수집기 이미지를 배포합니다. 포털에서 생성된 실행 명령을 복사하여 구성을 가져옵니다. 프록시를 구성해야 하는 경우 프록시 IP 주소와 포트를 추가합니다. 예를 들어, 프록시 세부 정보가 192.168.10.1:8080이면 업데이트된 실행 명령은 다음과 같습니다.

           (echo db3a7c73eb7e91a0db53566c50bab7ed3a755607d90bb348c875825a7d1b2fce) | docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e "CONSOLE=mod244533.us.portal.cloudappsecurity.com" -e "COLLECTOR=MyLogCollector" --security-opt apparmor:unconfined --cap-add=SYS_ADMIN --restart unless-stopped -a stdin -i microsoft/caslogcollector starter

   ![로그 수집기 만들기](./media/windows7.png)
8. `docker logs <collector_name>` 명령을 사용하여 수집기가 정상적으로 실행되고 있는지 확인합니다.

다음 메시지가 표시됩니다. **완료되었습니다.**

  ![ubuntu8](./media/ubuntu8.png)

### <a name="step-3---on-premises-configuration-of-your-network-appliances"></a>3단계 - 네트워크 어플라이언스의 온-프레미스 구성

대화 상자의 지침에 따라 FTP 디렉터리의 전용 Syslog 포트로 로그를 주기적으로 내보내도록 네트워크 방화벽 및 프록시를 구성합니다. 예:

    BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

### <a name="step-4---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>4단계 - Cloud App Security 포털에서 배포의 성공 여부 확인

**로그 수집기** 표에서 수집기 상태를 확인하고 상태가 **연결됨**인지 확인합니다. **생성됨**인 경우 로그 수집기 연결 및 구문 분석이 완료되지 않았을 수 있습니다.

 ![ubuntu9](./media/ubuntu9.png)

**거버넌스 로그**로 이동하여 로그가 주기적으로 포털에 업로드되는지 확인합니다.

배포하는 동안 문제가 발생한 경우 [Cloud Discovery 문제 해결](troubleshooting-cloud-discovery.md)을 참조하세요.

### 선택 사항 - 사용자 지정 연속 보고서 만들기 <a name="continuous-reports"></a>

로그가 Cloud App Security에 업로드 되고 보고서가 생성되었는지 확인합니다. 확인 후 사용자 지정 보고서를 만듭니다. Azure Active Directory 사용자 그룹을 기반으로 사용자 지정 검색 보고서를 만들 수 있습니다. 예를 들어 마케팅 부서의 클라우드 사용을 확인하려면 사용자 그룹 가져오기 기능을 사용하여 마케팅 그룹을 가져옵니다. 그런 다음, 이 그룹에 대한 사용자 지정 보고서를 만듭니다. IP 주소 태그 또는 IP 주소 범위를 기반으로 보고서를 사용자 지정할 수도 있습니다.

1. Cloud App Security 포털의 설정 코그 아래에서 Cloud Discovery 설정을 선택한 다음, **연속 보고서**를 선택합니다. 
2. **보고서 만들기** 단추를 클릭하고 필드를 입력합니다.
3. **필터** 아래에서 데이터 원본별, [가져온 사용자 그룹](user-groups.md)별 또는 [IP 주소 태그 및 범위](ip-tags.md)별로 데이터를 필터링할 수 있습니다. 

![사용자 지정 연속 보고서](./media/custom-continuous-report.png)

### 선택 사항 - 설치 관리자 서명 유효성 검사<a name="validate-signature"></a>

Docker 설치 프로그램이 Microsoft에서 서명되었는지 확인하려면:
1. 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.
2. **디지털 서명**을 클릭하여 **이 디지털 서명이 유효함**이 표시되는지 확인합니다.  
3. **Microsoft Corporation**이 **서명자 이름** 아래에 유일한 항목으로 나열되는지 확인합니다.  

![유효한 디지털 서명](./media/digital-signature-successful.png)

디지털 서명이 유효하지 않으면 **이 디지털 서명이 유효하지 않음**이 표시됩니다.

![잘못된 디지털 서명](./media/digital-signature-unsuccessful.png)

## <a name="next-steps"></a>다음 단계

[Cloud Discovery docker 배포 문제 해결](troubleshoot-docker.md)

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)

