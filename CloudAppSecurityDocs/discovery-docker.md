---
title: Cloud App Security에서 연속 보고서에 대한 자동 로그 업로드 구성
description: 이 문서에서는 Cloud App Security의 연속 보고서용 자동 로그 업로드를 구성하는 프로세스에 대해 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 04/04/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 99cca2a7a5fbc8bf57eb7a211bd32a28b102a78a
ms.sourcegitcommit: ec7ae3cd7648fa62d7a7925f8693dcb99b0b0d26
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59745969"
---
# <a name="configure-automatic-log-upload-for-continuous-reports"></a>연속 보고서에 대한 자동 로그 업로드 구성

*적용 대상: Microsoft Cloud App Security*

로그 수집기를 사용하여 네트워크에서 로그 업로드를 쉽게 자동화할 수 있습니다. 로그 수집기는 네트워크에서 실행되며 Syslog 또는 FTP를 통해 로그를 받습니다. 각 로그는 자동으로 처리 및 압축되고 포털에 전송됩니다. 로그 수집기로 파일의 FTP 전송이 완료되면 FTP 로그는 Microsoft Cloud App Security에 업로드됩니다. Syslog의 경우 로그 수집기는 수신한 로그를 디스크에 기록합니다. 그런 다음, 파일 크기가 40KB보다 크면 수집기가 파일을 Cloud App Security에 업로드합니다. 

로그를 Cloud App Security에 업로드한 후 백업 디렉터리로 이동합니다. 백업 디렉터리에는 마지막 20개 로그가 저장됩니다. 새 로그가 도착하면 이전 로그가 삭제됩니다. 로그 수집기 디스크 공간이 가득 찰 때마다 로그 수집기는 사용 가능한 디스크 공간이 확보될 때까지 새 로그를 삭제합니다. 이 경우 **자동으로 로그 업로드** 설정의 **로그 수집기** 탭에 경고가 표시됩니다.

자동 로그 파일 수집을 설정하기 전에 로그가 예상 로그 유형과 일치하는지 확인합니다. Cloud App Security가 특정 파일을 구문 분석할 수 있는지 확인합니다. 자세한 내용은 [Cloud Discovery에 트래픽 로그 사용](create-snapshot-cloud-discovery-reports.md#log-format)을 참조하세요.


> [!NOTE]
>-  Cloud App Security는 로그가 원래 형식으로 전달된다고 가정하고 SIEM 서버에서 로그 수집기로 로그 전달을 지원합니다. 그러나 로그 수집기를 방화벽 및/또는 프록시와 직접 통합하는 것이 좋습니다.
>- 로그 수집기는 데이터가 업로드되기 전에 압축합니다. 로그 수집기의 아웃바운드 트래픽은 수신하는 트래픽 로그의 10% 크기가 됩니다. 
>-  로그 수집기에 문제가 발생하는 경우 데이터를 48시간 동안 수신하지 못하면 알림을 받게 됩니다.
>

## <a name="deployment-modes"></a>배포 모드

로그 수집기에서는 다음 두 가지 배포 모드를 지원합니다.

-   **컨테이너**: [Ubuntu 온-프레미스](discovery-docker-ubuntu.md), [Azure의 Ubuntu](discovery-docker-ubuntu-azure.md) 또는 [RHEL 온-프레미스](discovery-docker-ubuntu.md)에서 Docker 이미지로 실행됩니다. 

-   **가상 어플라이언스**:  (사용 되지 않음) 하는 Hyper-v 또는 VMware 하이퍼바이저에서 이미지로 실행 됩니다




## <a name="next-steps"></a>다음 단계
 
[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)

