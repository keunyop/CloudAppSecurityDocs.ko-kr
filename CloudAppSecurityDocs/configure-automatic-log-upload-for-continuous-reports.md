---
title: "Cloud App Security에서 연속 보고서에 대한 자동 로그 업로드 구성 | Microsoft 문서"
description: "이 항목에서는 자동 Cloud Discovery 보고서를 만들기 위해 로그를 업로드하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/30/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c4123272-4111-4445-b6bd-2a1efd3e0c5c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d5f618feb038083dd9140a1c53d301788f561a4e
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="configure-automatic-log-upload-for-continuous-reports-on-a-virtual-appliance"></a>가상 어플라이언스 연속 보고서에 대한 자동 로그 업로드 구성

## <a name="technical-requirements"></a>기술 요구 사항
- 하이퍼바이저: HyperV 또는 VMware
- 디스크 공간: 250GB
- CPU: 2
- RAM: 4GB 
- 방화벽 설정: 
    - 로그 수집기가 인바운드 FTP 및 Syslog 트래픽을 수신하도록 허용
    - 로그 수집기가 포트 443에서 포털(예: contoso.cloudappsecurity.com)에 대한 아웃바운드 트래픽을 시작하도록 허용

  
## <a name="log-collector-performance"></a>로그 수집기 성능
로그 수집기는 시간당 최대 50GB의 로그 용량을 성공적으로 처리할 수 있습니다.
로그 수집 프로세스의 주요 병목 상태는 다음과 같습니다.
- 네트워크 대역폭 - 네트워크 대역폭은 로그 업로드 속도를 결정합니다.
- IT에서 할당한 가상 컴퓨터의 I/O 성능 - 로그가 로그 수집기의 디스크에 기록되는 속도를 결정합니다.
로그 수집기에는 로그가 도착하는 속도를 모니터링하고 업로드 속도와 비교하는 기본 제공 보안 메커니즘이 있습니다. 정체가 발생할 경우 로그 수집기에서 로그 파일 삭제를 시작합니다. 설치가 일반적으로 시간당 50GB를 초과할 경우 여러 로그 수집기 간에 트래픽을 분할하는 것이 좋습니다.

## <a name="set-up-and-configuration"></a>설정 및 구성  
  
### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>1단계 – 웹 포털 구성: 데이터 원본을 정의하고 로그 수집기에 연결  
  
1.  자동화된 업로드 설정 페이지로 이동합니다.  
    Cloud App Security 포털에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "설정 아이콘"), **로그 수집기**를 차례로 클릭합니다.  
  
3.  로그를 업로드하려는 각 방화벽 또는 프록시에 대해 일치하는 데이터 원본을 만듭니다.  
  
    a.  **데이터 원본 추가**를 클릭합니다.  
  
    b.  프록시 또는 방화벽에 **이름**을 지정합니다.  
  
    c.  **원본** 목록에서 어플라이언스를 선택합니다. 구체적으로 나열되지 않은 네트워크 어플라이언스에 사용하기 위하여 **사용자 지정 로그 형식**을 선택하는 경우 구성 지침은 [사용자 지정 로그 파서 작업](custom-log-parser.md)을 참조하세요.
  
    d.  예상 로그 형식 샘플과 로그를 비교합니다. 로그 파일 형식이 이 샘플과 일치하지 않는 경우 데이터 원본을 **기타**로 추가해야 합니다.  
  
    e.  **수신기 유형**을 **FTP** 또는 **Syslog**로 설정합니다. **Syslog**에 대해 **UDP** 또는 **TCP**를 선택합니다.  
  
    f.  해당 로그를 사용하여 네트워크의 트래픽을 검색할 수 있는 각 방화벽 및 프록시에 대해 이 프로세스를 반복합니다.  
  
4.  맨 위에 있는 **로그 수집기** 탭으로 이동합니다.  
  
    a.  **로그 수집기 추가**를 클릭합니다.  
  
    b.  로그 수집기에 **이름**을 지정합니다.  
  
    c.  수집기에 연결할 모든 **데이터 원본**을 선택하고 **업데이트**를 클릭하여 구성을 저장한 후 액세스 토큰을 생성합니다.  
![검색 데이터 원본](./media/discovery-data-sources.png)
  
  > [!NOTE] 
  > - 단일 로그 수집기로 여러 데이터 원본을 처리할 수 있습니다.
  > - Cloud App Security와 통신하도록 로그 수집기를 구성하는 경우 정보가 필요하므로 화면의 내용을 복사합니다. Syslog를 선택한 경우 이 정보에는 Syslog 수신기가 수신 대기하는 포트에 대한 정보가 포함됩니다.
4.  Hyper-V 또는 VMWare를 클릭하여 새 로그 수집기 가상 컴퓨터를 **다운로드**하고 포털에서 받은 암호를 사용하여 파일의 압축을 풉니다.  
  
### <a name="step-2--on-premises-deployment-of-the-virtual-machine-and-network-configuration"></a>2단계 – 가상 컴퓨터 및 네트워크 구성의 온-프레미스 배포   

> [!NOTE] 
> 다음 단계에서는 Hyper-V에서의 배포에 관해 설명합니다. VM 하이퍼바이저의 배포 단계는 약간 다릅니다.  

1.  Hyper-V 관리자를 엽니다.  
  
2.  **새로 만들기**, **가상 컴퓨터**를 차례로 선택하고 **다음**을 클릭합니다.  
 ![검색 HyperV 가상 컴퓨터](./media/discovery-hyperv-virtual-machine.png "검색 HyperV 가상 컴퓨터")  
  
3.  새 가상 컴퓨터의 **이름**(예: CloudAppSecurityLogCollector01)을 지정하고 **다음**을 클릭합니다.  
  
4.  **1세대**를 선택하고 **다음**을 클릭합니다.  
  
5.  **시작 메모리**를 **4096MB**로 변경합니다.  
        
6. 이 가상 컴퓨터에 대해 **동적 메모리 사용**을 선택하고 **다음**을 클릭합니다.  
  
7.  사용 가능한 경우 네트워크 **연결**을 선택하고 **다음**을 클릭합니다.  
  
8.  **기존 가상 하드 디스크 사용**을 선택한 다음 다운로드한 Zip 파일에 포함된 .**vhd** 파일을 선택합니다.  
  
9.  **다음** 을 클릭하고 **마침**을 클릭합니다.  
    컴퓨터가 Hyper-V 환경에 추가됩니다.  
  
9. **Virtual Machines** 테이블에서 컴퓨터를 클릭한 다음 **시작**을 클릭합니다.   
  
10. 로그 수집기 가상 컴퓨터에 연결하여 DHCP 주소가 할당되었는지 확인합니다. 가상 컴퓨터를 클릭하고 **연결**을 선택합니다. 로그인 프롬프트가 표시됩니다. IP 주소가 표시되면 터미널/SSH 도구를 사용하여 가상 컴퓨터에 연결할 수 있습니다.  IP 주소가 표시되지 않으면 Hyper-V/VMWare 연결 도구를 사용하여 위에서 로그 수집기를 만들 때 복사한 자격 증명으로 로그인합니다. 다음 명령을 실행하여 암호를 변경하고 네트워크 구성 유틸리티를 사용하여 가상 컴퓨터를 구성할 수 있습니다.
```
sudo network_config
```
> [!NOTE]
> 가상 컴퓨터는 DHCP 서버에서 IP 주소를 가져오도록 미리 구성되어 있습니다. 고정 IP 주소, 기본 게이트웨이, 호스트 이름, DNS 서버 및 NTPS를 구성해야 하는 경우 **network_config** 유틸리티를 사용하거나 수동으로 변경할 수 있습니다.


이 시점에서 로그 수집기가 네트워크에 연결되어야 하며 Cloud App Security 포털에 액세스할 수 있어야 합니다.  

### <a name="step-3--on-premises-configuration-of-the-log-collection"></a>3단계 – 로그 수집의 온-프레미스 구성 
처음으로 로그 수집기에 로그인하고 다음과 같이 포털에서 로그 수집기의 구성을 가져옵니다. 

1.  포털에서 제공된 대화형 관리자 자격 증명을 사용하여 SSH를 통해 로그 수집기에 로그인합니다. (처음으로 콘솔에 로그인하는 경우 암호를 변경해야 하며 암호를 변경한 후에는 다시 로그인해야 합니다. 터미널 세션을 사용하는 경우 터미널 세션을 다시 시작해야 할 수 있습니다. )
2.  로그 수집기를 만들 때 제공된 액세스 토큰을 사용하여 수집기 구성 유틸리티를 실행합니다.```sudo collector_config <access token> ```
3. 콘솔 도메인을 입력합니다. 예를 들면 다음과 같습니다. ```contoso.portal.cloudappsecurity.com``` 이 값은 Cloud App Security 포털에 로그인한 후에 보이는 URL에서 사용할 수 있습니다. 

4. 예를 들어, 위 그림의 **CloudAppSecurityLogCollector01** 또는 **NewYork**과 같이 구성할 로그 수집기의 이름을 입력합니다.

5.  다음과 같이 포털에서 로그 수집기의 구성을 가져옵니다.  
  
      a.  포털에서 제공된 대화형 관리자 자격 증명을 사용하여 SSH를 통해 로그 수집기에 로그인합니다.  
  
      b.  ```sudo collector_config \<access token>``` 명령에서 제공된 액세스 토큰을 사용하여 수집기 구성 유틸리티를 실행합니다.  
     
      c.  콘솔 도메인을 입력합니다. 예를 들면 다음과 같습니다.``` contoso.portal.cloudappsecurity.com ```
  
      d. 구성하려는 로그 수집기의 이름을 입력합니다. 예를 들면 다음과 같습니다.``` CloudAppSecurityLogCollector01  ```

### <a name="step-4---on-premises-configuration-of-your-network-appliances"></a>4 단계 - 네트워크 장치의 온-프레미스 구성

대화 상자의 지침에 따라 FTP 디렉터리의 전용 Syslog 포트로 로그를 주기적으로 내보내도록 네트워크 방화벽 및 프록시를 구성합니다. 예를 들면 다음과 같습니다.  
  
     `London Zscaler - Destination path: 614`  
  
     BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\  
  
### <a name="step-5---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>5 단계 - Cloud App Security 포털에서 배포의 성공 여부 확인

**로그 수집기** 표에서 수집기 상태를 확인하고 상태가 **연결됨**인지 확인합니다. **작성됨**인 경우에는 로그 수집기 연결 및 구문 분석이 완료되지 않은 것일 수 있습니다.

![로그 수집기 상태](./media/log-collector-status.png)

거버넌스 로그로 이동하여 로그가 주기적으로 포털에 업로드되고 있는지 확인합니다.  
  
배포하는 동안 문제가 발생할 경우 [Cloud Discovery 문제 해결](troubleshooting-cloud-discovery.md)을 참조하세요.

### <a name="optional---create-custom-continuous-reports"></a>선택 사항 - 사용자 지정 연속 보고서 만들기

로그가 Cloud App Security에 업로드되고 보고서가 생성되고 있는지 확인한 후 사용자 지정 보고서를 만들 수 있습니다. 이제 Azure Active Directory 사용자 그룹을 기반으로 사용자 지정 검색 보고서를 만들 수 있습니다. 예를 들어 마케팅 부서의 클라우드 사용을 확인하려면 사용자 그룹 가져오기 기능을 사용하여 마케팅 그룹을 가져오고 이 그룹에 대한 사용자 지정 보고서를 만들면 됩니다. IP 주소 태그 또는 IP 주소 범위를 기반으로 보고서를 사용자 지정할 수도 있습니다.

1. Cloud App Security 포털의 [설정] 코그 아래에서 **Cloud Discovery settings**(Cloud Discovery 설정)를 선택하고 **연속 보고서 관리**를 선택합니다. 
2. **보고서 만들기** 단추를 클릭하고 필드를 입력합니다.
3. **필터** 아래에서 데이터 원본별, [가져온 사용자 그룹](user-groups.md)별 또는 [IP 주소 태그 및 범위](ip-tags.md)별로 데이터를 필터링할 수 있습니다. 

![사용자 지정 연속 보고서](./media/custom-continuous-report.png)

## <a name="see-also"></a>참고 항목  
[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
    
      
  