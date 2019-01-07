---
title: Cloud Discovery 배포 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud Discovery 작업을 시작하기 위한 설정 절차에 대해 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 0ad041c73f1bb8871e08357e6d85269ef20f3903
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53175909"
---
# <a name="set-up-cloud-discovery"></a>Cloud Discovery 설정

*적용 대상: Microsoft Cloud App Security*

Cloud Discovery는 16,000개 이상의 클라우드 앱이 포함된 Microsoft Cloud App Security 클라우드 앱 카탈로그에 대한 트래픽 로그를 분석합니다. 이 앱은 70개를 넘는 위험 요인을 기준으로 순위 및 점수를 매겨 클라우드 사용, 섀도 IT 및 위험 섀도 IT에 대한 지속적인 가시성을 제공합니다.

## <a name="snapshot-and-continuous-risk-assessment-reports"></a>스냅숏 및 연속 위험 평가 보고서 

두 가지 유형의 보고서를 생성할 수 있습니다. 

- **스냅숏 보고서** - 방화벽 및 프록시에서 수동으로 업로드하는 트래픽 로그 집합에 대한 임시 가시성을 제공합니다.

- **연속 보고서** - Cloud App Security를 사용하여 네트워크에서 전달되는 모든 로그를 분석합니다. 이러한 보고서는 모든 데이터에 대해 향상된 가시성을 제공하고 Machine Learning 변칙 검색 엔진이나 사용자가 정의한 사용자 지정 정책을 사용하여 비정상적인 사용을 자동으로 식별합니다. 이러한 보고서는 다음과 같은 방법으로 연결하여 만들 수 있습니다.

  - [Windows Defender ATP 통합](wdatp-integration.md): Cloud App Security는 Cloud Discovery 롤아웃을 간소화하고, Cloud Discovery 기능을 회사 네트워크 너머로 확장하고, 머신 기반 조사를 사용하기 위해 기본적으로 Windows Defender ATP(Advanced Threat Protection)와 통합됩니다.
  - [로그 수집기](discovery-docker.md): 로그 수집기를 사용하여 네트워크에서 로그 업로드를 쉽게 자동화할 수 있습니다. 로그 수집기는 네트워크에서 실행되며 Syslog 또는 FTP를 통해 로그를 받습니다.
  - [Zscaler 통합](zscaler-integration.md): Cloud App Security와 Zscaler를 모두 사용하는 경우 두 제품을 통합하여 보안 Cloud Discovery 환경을 향상할 수 있습니다. Cloud App Security와 Zscaler는 함께 Zscaler 포털에서 Cloud Discovery의 원활한 배포, 비사용 권한 앱의 자동 차단 및 위험 평가를 직접 제공합니다.

## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>로그 프로세스 흐름: 원시 데이터에서 위험 평가로

위험 평가 생성 프로세스는 다음과 같은 단계로 구성됩니다. 이 프로세스는 처리되는 데이터의 양에 따라 몇 분에서 몇 시간이 걸립니다.  

- **업로드** - 네트워크의 웹 트래픽 로그가 포털에 업로드됩니다.  

- **구문 분석** – Cloud App Security에서 각 데이터 원본에 대한 전용 파서를 사용하여 트래픽 로그에서 트래픽 데이터를 구문 분석하고 추출합니다.  

- **분석** - 클라우드 앱 카탈로그를 기준으로 트래픽 데이터를 분석하여 16,000개를 넘는 클라우드 앱을 식별하고 해당 위험 점수를 평가합니다. 활성 사용자와 IP 주소도 분석의 일부로 식별됩니다.  

- **보고서 생성** - 로그 파일에서 추출된 데이터의 위험 평가 보고서가 생성됩니다.


>[!NOTE]
> 연속 보고서 데이터는 하루에 두 번 분석됩니다.


## <a name="next-steps"></a>다음 단계

[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[연속 보고서에 대한 자동 로그 업로드 구성](configure-automatic-log-upload-for-continuous-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)