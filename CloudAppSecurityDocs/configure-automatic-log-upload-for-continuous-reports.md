---
title: "연속 보고서에 대한 자동 로그 업로드 구성 | Microsoft 문서"
description: "이 항목에서는 자동 Cloud Discovery 보고서를 만들기 위해 로그를 업로드하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c4123272-4111-4445-b6bd-2a1efd3e0c5c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 9672336d69f19875d160eb414bf3ca2c525692e1


---

# <a name="configure-automatic-log-upload-for-continuous-reports"></a>연속 보고서에 대한 자동 로그 업로드 구성
자동 로그 파일 수집을 설정하기 전에 로그가 예상 로그 유형과 일치하는지 확인하여 Cloud App Security에서 특정 파일을 구문 분석할 수 있도록 합니다. 

## <a name="technical-requirements"></a>기술 요구 사항
- 하이퍼바이저: HyperV 또는 VMware
- 디스크 공간: 250GB
- CPU: 2
- RAM: 4GB 
- 방화벽 설정: 
- 로그 수집기가 인바운드 FTP 및 Syslog 트래픽을 수신하도록 허용
- 로그 수집기가 포트 443에서 포털(예: contoso.cloudappsecurity.com)에 대한 아웃바운드 트래픽을 시작하도록 허용

  
## <a name="set-up-automatic-log-file-collection"></a>자동 로그 파일 수집 설정  
  
로그 수집기를 사용하여 네트워크에서 로그 업로드를 쉽게 자동화할 수 있습니다. 로그 수집기는 네트워크에서 실행되며 Syslog 또는 FTP를 통해 로그를 받습니다. 각 로그는 자동으로 처리 및 압축되고 포털에 전송됩니다. FTP 로그는 파일이 로그 수집기로 FTP 전송을 완료한 후 Cloud App Security에 업로드되며 Syslog의 경우 로그 수집기가 수신한 로그를 20분마다 디스크에 쓴 다음 파일을 Cloud App Security에 업로드합니다.  로그 수집기 가상 컴퓨터는Hyper-V(VHD 형식) 및 VMware 하이퍼바이저(OVF 형식)에 사용할 수 있으며 250GB 디스크 공간, 2개 CPU 및 4GB RAM이 필요합니다. 
     
  
     The log collector VHD image can be downloaded and run on Azure servers.  
  
2.  자동화된 업로드 설정 페이지로 이동합니다.  
    Cloud App Security 포털에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "settings icon"), **Cloud Discovery 설정**을 차례로 클릭하고 **자동으로 로그 업로드** 탭을 선택합니다.  
  
3.  로그를 업로드하려는 각 방화벽 또는 프록시에 대해 일치하는 데이터 원본을 만듭니다.  
  
    1.  **데이터 원본 추가**를 클릭합니다.  
  
    2.  프록시 또는 방화벽에 **이름**을 지정합니다.  
  
    3.  **원본** 목록에서 어플라이언스를 선택합니다.  
  
    4.  예상 로그 형식 샘플과 로그를 비교합니다. 로그 파일 형식이 이 샘플과 일치하지 않는 경우 데이터 원본을 **기타**로 추가해야 합니다.  
  
    5.  **수신기 유형**을 **FTP** 또는 **Syslog**로 설정합니다.  
  
         **Syslog**에 대해 **UDP** 또는 **TCP**를 선택합니다.  
  
    6.  해당 로그를 사용하여 네트워크의 트래픽을 검색할 수 있는 각 방화벽 및 프록시에 대해 이 프로세스를 반복합니다.  
  
4.  맨 위에 있는 **로그 수집기** 탭으로 이동합니다.  
  
    1.  **로그 수집기 추가**를 클릭합니다.  
  
    2.  로그 수집기에 **이름**을 지정합니다.  
  
    3.  수집기에 연결하려는 **데이터 원본**을 모두 선택하고 **업데이트**를 클릭합니다.  
  
         > [!NOTE] 
       > Cloud App Security와 통신하도록 로그 수집기를 구성하는 경우 정보가 필요하므로 화면의 내용을 복사합니다. Syslog를 선택한 경우 이 정보에는 Syslog 수신기가 수신 대기하는 포트에 대한 정보가 포함됩니다.
         
![검색 데이터 원본](./media/discovery-data-sources.png)
> [!NOTE] 
         > 단일 로그 수집기로 여러 데이터 원본을 처리할 수 있습니다.
  
4.  Hyper-V 또는 VMWare를 클릭하여 새 로그 수집기 가상 컴퓨터를 **다운로드**하고 포털에서 받은 암호를 사용하여 파일의 압축을 풉니다.  
  
## <a name="set-up-your-virtual-machine-in-hyperv"></a>Hyper-V에서 가상 컴퓨터 설정:  
  
1.  Hyper-V 관리자를 엽니다.  
  
2.  **새로 만들기**, **가상 컴퓨터**를 차례로 선택하고 **다음**을 클릭합니다.  
  
             ![discovery hyperv virtual machine](./media/discovery-hyperv-virtual-machine.png "discovery hyperv virtual machine")  
  
3.  새 가상 컴퓨터의 **이름**(예: CloudAppSecurityLogCollector01)을 지정하고 **다음**을 클릭합니다.  
  
4.  **1세대**를 선택하고 **다음**을 클릭합니다.  
  
5.  **시작 메모리**를 **4096MB**로 변경합니다.  
        
6. 이 가상 컴퓨터에 대해 **동적 메모리 사용**을 선택하고 **다음**을 클릭합니다.  
  
7.  사용 가능한 경우 네트워크 **연결**을 선택하고 **다음**을 클릭합니다.  
  
8.  **기존 가상 하드 디스크 사용**을 선택한 다음 다운로드한 Zip 파일에 포함된 .**vhd** 파일을 선택합니다.  
  
9.  **다음** 을 클릭하고 **마침**을 클릭합니다.  
  
             The machine will be added to your Hyper-V environment.  
  
9. **Virtual Machines** 테이블에서 컴퓨터를 클릭한 다음 **시작**을 클릭합니다.   
  
10. 로그 수집기 가상 컴퓨터에 연결하여 DHCP 주소가 할당되었는지 확인합니다. 가상 컴퓨터를 클릭하고 **연결**을 선택합니다. 로그인 프롬프트가 표시됩니다. IP 주소가 표시되면 터미널/SSH 도구를 사용하여 가상 컴퓨터에 연결할 수 있습니다.  IP 주소가 표시되지 않으면 Hyper-V/VMWare 연결 도구를 사용하여 위에서 로그 수집기를 만들 때 복사한 자격 증명으로 로그인합니다. 다음 명령을 실행하여 가상 컴퓨터를 구성하고 암호를 변경할 수 있습니다.
```
sudo network_config
```
> [!NOTE]
> 가상 컴퓨터는 DHCP 서버에서 IP 주소를 가져오도록 미리 구성되어 있습니다. 고정 IP 주소, 기본 게이트웨이, 호스트 이름, DNS 서버 및 NTPS를 구성해야 하는 경우 **network_config** 유틸리티를 사용하거나 수동으로 변경할 수 있습니다.


이 시점에서 로그 수집기가 네트워크에 연결되어야 하며 Cloud App Security 포털에 액세스할 수 있어야 합니다.  

## <a name="log-in-and-import"></a>로그인 및 가져오기 
처음으로 로그 수집기에 로그인하고 다음과 같이 포털에서 로그 수집기의 구성을 가져옵니다. 

1.  포털에서 제공된 대화형 관리자 자격 증명을 사용하여 SSH를 통해 로그 수집기에 로그인합니다. (처음으로 콘솔에 로그인하는 경우 암호를 변경해야 하며 암호를 변경한 후에는 다시 로그인해야 합니다. 터미널 세션을 사용하는 경우 터미널 세션을 다시 시작해야 할 수 있습니다. )
2.  로그 수집기를 만들 때 제공된 액세스 토큰을 사용하여 수집기 구성 유틸리티를 실행합니다. 

```
sudo collector_config <access token>
```

3. 콘솔 도메인을 입력합니다. 예를 들면 다음과 같습니다.

```
contoso.portal.cloudappsecurity.com
```

이 도메인은 Cloud App Security 포털에 로그인한 후 표시되는 URL에서 사용할 수 있습니다. 
 

4. 구성하려는 로그 수집기의 이름을 입력합니다. 예를 들면 다음과 같습니다.

위의 그림에서 **CloudAppSecurityLogCollector01** 또는 **NewYork**
 
8.  다음과 같이 포털에서 로그 수집기의 구성을 가져옵니다.  
  
      1.  포털에서 제공된 대화형 관리자 자격 증명을 사용하여 SSH를 통해 로그 수집기에 로그인합니다.  
  
       2.  **sudo collector_config \<access token>** 명령에서 제공된 액세스 토큰을 사용하여 수집기 구성 유틸리티를 실행합니다.  
  
             콘솔 도메인을 입력합니다. 예를 들면 다음과 같습니다.  
  
             **contoso.portal.cloudappsecurity.com ** 
  
             구성하려는 로그 수집기의 이름을 입력합니다. 예를 들면 다음과 같습니다.  
  
             **CloudAppSecurityLogCollector01**  
  
5.  대화 상자의 지침에 따라 FTP 디렉터리의 전용 Syslog 포트로 로그를 주기적으로 내보내도록 네트워크 방화벽 및 프록시를 구성합니다. 예를 들면 다음과 같습니다.  
  
     `London Zscaler - Destination path: 614`  
  
     `SF Blue Coat - Destination path: \\CloudAppSecurityCollector01\BlueCoat\`  
  
6.  거버넌스 로그를 사용하여 로그가 주기적으로 포털에 업로드되고 있는지 확인합니다.  
  
## <a name="log-collector-performance"></a>로그 수집기 성능
로그 수집기는 시간당 최대 50GB의 로그 용량을 성공적으로 처리할 수 있습니다.

로그 수집 프로세스의 주요 병목 상태는 다음과 같습니다.
* 네트워크 대역폭 - 네트워크 대역폭은 로그 업로드 속도를 결정합니다.
* IT에서 할당한 가상 컴퓨터의 I/O 성능 - 로그가 로그 수집기의 디스크에 기록되는 속도를 결정합니다.

로그 수집기에는 로그가 도착하는 속도를 모니터링하고 업로드 속도와 비교하는 기본 제공 보안 메커니즘이 있습니다. 정체가 발생할 경우 로그 수집기에서 로그 파일 삭제를 시작합니다. 설치가 일반적으로 시간당 50GB를 초과할 경우 여러 로그 수집기 간에 트래픽을 분할하는 것이 좋습니다.


<!--HONumber=Oct16_HO4-->

