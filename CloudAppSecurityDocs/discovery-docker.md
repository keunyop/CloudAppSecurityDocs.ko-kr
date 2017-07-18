---
title: "연속 보고서에 대한 자동 로그 업로드 구성 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security에서 연속 보고서를 위한 자동 로그 업로드를 구성하는 프로세스에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/9/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9f17366c62b202432d8b0c750290b4915f64c929
ms.sourcegitcommit: b2e3af9d0a62dcb6410cc3992183c2888bdf6a2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2017
---
# <a name="configure-automatic-log-upload-for-continuous-reports"></a>연속 보고서에 대한 자동 로그 업로드 구성


로그 수집기를 사용하여 네트워크에서 로그 업로드를 쉽게 자동화할 수 있습니다. 로그 수집기는 네트워크에서 실행되며 Syslog 또는 FTP를 통해 로그를 받습니다. 각 로그는 자동으로 처리 및 압축되고 포털에 전송됩니다. 파일에서 로그 수집기로 FTP 전송이 완료되면 FTP 로그가 Cloud App Security에 업로드됩니다.  Syslog의 경우 로그 수집기에서 수신한 로그를 디스크에 쓴 다음, 파일 크기가 40KB보다 커지면 Cloud App Security에 파일을 업로드합니다.

로그는 Cloud App Security에 업로드된 후 특정 시점에 마지막 20개 로그를 저장한 백업 디렉터리로 이동합니다. 새 로그가 도착하면 이전 로그가 삭제됩니다. 로그 수집기 디스크 공간이 가득 차면 로그 수집기는 사용 가능한 디스크 공간이 확보될 때까지 새 로그를 삭제합니다.

자동 로그 파일 수집을 설정하기 전에 로그가 예상 로그 유형과 일치하는지 확인하여 Cloud App Security에서 특정 파일을 구문 분석할 수 있도록 합니다.

> [!NOTE]
> Cloud App Security는 로그가 원래 형식으로 전달된다고 가정하고 SIEM 서버에서 로그 수집기로 로그 전달을 지원합니다. 그러나 로그 수집기를 방화벽 및/또는 프록시와 직접 통합하는 것이 좋습니다.

## <a name="deployment-modes"></a>배포 모드

로그 수집기에서는 다음 두 가지 배포 모드를 지원합니다.

-   **컨테이너**(*Docker CE 기반*): 온-프레미스나 Azure의 [Windows](discovery-docker-windows.md) 및 [Ubuntu](discovery-docker-ubuntu.md)에서 Docker 이미지로 실행합니다.

-   **가상 어플라이언스**(*더 이상 사용되지 않음*):  [Hyper-V 또는 VMware 하이퍼바이저를 통한 이미지로 실행](configure-automatic-log-upload-for-continuous-reports.md)




## <a name="see-also"></a>참고 항목
 
[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)

