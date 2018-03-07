---
title: "연속 보고서에 대한 자동 로그 업로드 구성 | Microsoft 문서"
description: "이 항목에서는 온-프레미스 서버의 Ubuntu에서 Docker를 사용하여 Cloud App Security의 연속 보고서용 자동 로그 업로드를 구성하는 프로세스에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/25/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cc29a6cb-1c03-4148-8afd-3ad47003a1e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 13110a717b907decd2bafc938a01548f16d7bd76
ms.sourcegitcommit: 85d90d51e9e265d077f38b0188bcfdab2ce63ed1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="docker-on-ubuntu-and-rhel-on-premises"></a>Ubuntu 및 RHEL 온-프레미스의 Docker


## <a name="technical-requirements"></a>기술 요구 사항

-   OS: Ubuntu 14.04 이상(Ubuntu 17.10을 지원하는 안정적인 버전의 Docker 없음)

-   디스크 공간: 250GB

-   CPU: 2

-   RAM: 4GB

-   [네트워크 요구 사항](network-requirements#log-collector)에 설명된 대로 방화벽 설정


## <a name="log-collector-performance"></a>로그 수집기 성능

로그 수집기는 시간당 최대 50GB의 로그 용량을 성공적으로 처리할 수 있습니다. 로그 수집 프로세스의 주요 병목 상태는 다음과 같습니다.

-   네트워크 대역폭 - 네트워크 대역폭은 로그 업로드 속도를 결정합니다.

-   IT에서 할당한 가상 컴퓨터의 I/O 성능 - 로그가 로그 수집기의 디스크에 기록되는 속도를 결정합니다. 로그 수집기에는 로그가 도착하는 속도를 모니터링하고 업로드 속도와 비교하는 기본 제공 보안 메커니즘이 있습니다. 정체가 발생할 경우 로그 수집기에서 로그 파일 삭제를 시작합니다. 설치가 일반적으로 시간당 50GB를 초과할 경우 여러 로그 수집기 간에 트래픽을 분할하는 것이 좋습니다.

## <a name="set-up-and-configuration"></a>설정 및 구성  

### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>1단계 – 웹 포털 구성: 데이터 원본을 정의하고 로그 수집기에 연결

1.  자동화된 업로드 설정 페이지로 이동합니다.  <br></br>Cloud App Security 포털에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png), **로그 수집기**를 차례로 클릭합니다.

2.  로그를 업로드하려는 각 방화벽 또는 프록시에 대해 일치하는 데이터 원본을 만듭니다.

    ![ubuntu1](./media/ubuntu1.png)

    a. **데이터 원본 추가**를 클릭합니다.

    b. 프록시 또는 방화벽에 **이름**을 지정합니다.

    c. **원본** 목록에서 어플라이언스를 선택합니다. 구체적으로 나열되지 않은 네트워크 어플라이언스에 사용하기 위하여 **사용자 지정 로그 형식**을 선택하는 경우 구성 지침은 [사용자 지정 로그 파서 작업](custom-log-parser.md)을 참조하세요.

    d. 예상 로그 형식 샘플과 로그를 비교합니다. 로그 파일 형식이 이 샘플과 일치하지 않는 경우 데이터 원본을 **기타**로 추가해야 합니다.

    e. **수신기 유형**을 **FTP**, **FTPS**, **Syslog – UDP** 또는 **Syslog – TCP** 또는 **Syslog – TLS**로 설정합니다.
    
     >[!NOTE]
     >보안 전송 프로토콜(FTPS 및 Syslog - TLS)과 통합하려면 종종 추가 설정 또는 방화벽/프록시가 필요합니다.

    f. 해당 로그를 사용하여 네트워크의 트래픽을 검색할 수 있는 각 방화벽 및 프록시에 대해 이 프로세스를 반복합니다.

3.  맨 위에 있는 **로그 수집기** 탭으로 이동합니다.

    a. **로그 수집기 추가**를 클릭합니다.

    b. 로그 수집기에 **이름**을 지정합니다.

    c. Docker를 배포하는 데 사용할 컴퓨터의 **호스트 IP 주소**를 입력합니다. 
       
       > [!NOTE]
       > 호스트 이름을 확인할 DNS 서버(또는 이와 동등한)가 있으면 호스트 IP 주소를 컴퓨터 이름으로 바꿀 수 있습니다.

    d. 수집기에 연결할 모든 **데이터 원본**을 선택하고 **업데이트**를 클릭하여 구성을 저장한 후 다음 배포 단계를 확인합니다.

    ![ubuntu2](./media/ubuntu2.png)

     >  [!NOTE]
     > - 단일 로그 수집기로 여러 데이터 원본을 처리할 수 있습니다.
     > - Cloud App Security와 통신하도록 로그 수집기를 구성하는 경우 정보가 필요하므로 화면의 내용을 복사합니다. Syslog를 선택한 경우 이 정보에는 Syslog 수신기가 수신 대기하는 포트에 대한 정보가 포함됩니다.

4.  추가 배포 정보가 표시됩니다. 대화 상자의 실행 명령을 **복사**합니다. 클립보드에 복사 아이콘 ![클립보드에 복사 아이콘](./media/copy-icon.png)을 사용할 수 있습니다.

6.  예상 데이터 원본 구성 **내보내기**를 수행합니다. 이 구성에서는 어플라이언스에서 로그 내보내기를 설정하는 방법을 설명합니다.

   ![로그 수집기 만들기](./media/windows7.png)

### <a name="step-2--on-premises-deployment-of-your-machine"></a>2단계 - 컴퓨터의 온-프레미스 배포

> [!NOTE]
> 다음 단계에서는 Ubuntu에서의 배포를 설명합니다. 다른 플랫폼의 경우 배포 단계가 약간 다릅니다.

1.  Ubuntu 컴퓨터에서 터미널을 엽니다.

2.  `sudo -i` 명령을 사용하여 루트 권한으로 변경합니다.

3. 네트워크의 프록시를 우회하려면 다음 두 명령을 실행합니다.
        
        export http_proxy='<IP>:<PORT>' (e.g. 168.192.1.1:8888)
        export https_proxy='<IP>:<PORT>'

3.  [소프트웨어 라이선스 조건](https://go.microsoft.com/fwlink/?linkid=862492)에 동의하는 경우 다음 명령을 실행하여 이전 버전을 제거하고 Docker CE를 설치합니다.

    `curl -o /tmp/MCASInstallDocker.sh
    https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh
    && chmod +x /tmp/MCASInstallDocker.sh; /tmp/MCASInstallDocker.sh`

     > [!NOTE] 
     > 이 명령이 프록시 인증서의 유효성을 검사하지 못하면 시작 시 `curl -k`을(를) 사용하여 명령을 실행합니다.
    
    ![ubuntu5](./media/ubuntu5.png)

4.  수집기 구성을 가져와서 호스팅 컴퓨터에 수집기 이미지를 배포합니다. 포털에서 생성된 실행 명령을 복사하여 이 작업을 수행합니다. 프록시를 구성해야 하는 경우 프록시 IP 주소와 포트를 추가합니다. 예를 들어, 프록시 세부 정보가 192.168.10.1:8080이면 업데이트된 실행 명령은 다음과 같습니다.

            (echo 6f19225ea69cf5f178139551986d3d797c92a5a43bef46469fcc997aec2ccc6f) | docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e "PUBLICIP='192.2.2.2'" -e "PROXY=192.168.10.1:8080" -e "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt apparmor:unconfined --cap-add=SYS_ADMIN --restart unless-stopped -a stdin -i microsoft/caslogcollector starter

   ![로그 수집기 만들기](./media/windows7.png)

5.  `docker logs \<collector_name\>` 명령을 실행하여 수집기가 정상적으로 실행되고 있는지 확인합니다.

**Finished successfully!**라는 메시지가 표시되어야 합니다

  ![ubuntu8](./media/ubuntu8.png)

### <a name="step-3---on-premises-configuration-of-your-network-appliances"></a>3단계 - 네트워크 어플라이언스의 온-프레미스 구성

대화 상자의 지침에 따라 FTP 디렉터리의 전용 Syslog 포트로 로그를 주기적으로 내보내도록 네트워크 방화벽 및 프록시를 구성합니다. 예를 들면 다음과 같습니다.

    BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

### <a name="step-4---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>4단계 - Cloud App Security 포털에서 배포의 성공 여부 확인

**로그 수집기** 표에서 수집기 상태를 확인하고 상태가 **연결됨**인지 확인합니다. **작성됨**인 경우에는 로그 수집기 연결 및 구문 분석이 완료되지 않은 것일 수 있습니다.

 ![ubuntu9](./media/ubuntu9.png)

**거버넌스 로그**로 이동하여 로그가 주기적으로 포털에 업로드되고 있는지 확인할 수도 있습니다.

배포하는 동안 문제가 발생할 경우 [Cloud Discovery 문제 해결](troubleshooting-cloud-discovery.md)을 참조하세요.

### <a name="optional---create-custom-continuous-reports"></a>선택 사항 - 사용자 지정 연속 보고서 만들기

로그가 Cloud App Security에 업로드되고 보고서가 생성되고 있는지 확인한 후 사용자 지정 보고서를 만들 수 있습니다. 이제 Azure Active Directory 사용자 그룹을 기반으로 사용자 지정 검색 보고서를 만들 수 있습니다. 예를 들어 마케팅 부서의 클라우드 사용을 확인하려면 사용자 그룹 가져오기 기능을 사용하여 마케팅 그룹을 가져오고 이 그룹에 대한 사용자 지정 보고서를 만들면 됩니다. IP 주소 태그 또는 IP 주소 범위를 기반으로 보고서를 사용자 지정할 수도 있습니다.

1. Cloud App Security 포털의 [설정] 코그 아래에서 **Cloud Discovery settings**(Cloud Discovery 설정)를 선택하고 **연속 보고서 관리**를 선택합니다. 
2. **보고서 만들기** 단추를 클릭하고 필드를 입력합니다.
3. **필터** 아래에서 데이터 원본별, [가져온 사용자 그룹](user-groups.md)별 또는 [IP 주소 태그 및 범위](ip-tags.md)별로 데이터를 필터링할 수 있습니다. 

![사용자 지정 연속 보고서](./media/custom-continuous-report.png)

## <a name="see-also"></a>참고 항목

[Cloud Discovery docker 배포 문제 해결](troubleshoot-docker.md)

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)

