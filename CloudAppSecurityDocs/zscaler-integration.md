---
title: Cloud App Security와 Zscaler 통합
description: 이 문서에서는 원활한 Cloud Discovery 및 승인되지 않은 앱의 자동 차단을 위해 Microsoft Cloud App Security와 Zscaler를 통합하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8abeab8e-3b7a-46a7-bbec-9aaf26f778a8
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: d26ba74ff95df4fc2def9cfff0acd41dcef358a4
ms.sourcegitcommit: c24732bc40350c3cf416640b7d15f3c6f7be371d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2019
ms.locfileid: "55086399"
---
# <a name="integrate-cloud-app-security-with-zscaler"></a>Cloud App Security와 Zscaler 통합

*적용 대상: Microsoft Cloud App Security*

Cloud App Security와 Zscaler를 모두 사용하는 경우 두 제품을 통합하여 보안 Cloud Discovery 환경을 향상할 수 있습니다. 독립 실행형 클라우드 프록시로서 Zscaler는 조직의 트래픽을 모니터링하여 트랜잭션을 차단하기 위한 정책을 설정할 수 있게 해줍니다. Cloud App Security와 Zscaler는 함께 다음 기능을 제공합니다.

- Cloud Discovery의 원활한 배포 - Zscaler를 사용하여 트래픽을 프록시하고 Cloud App Security로 보내면 Cloud Discovery를 사용하도록 설정하기 위해 네트워크 엔드포인트에 로그 수집기를 설치할 필요가 없습니다.
- Zscaler의 차단 기능은 Cloud App Security에서 비사용 권한으로 설정한 앱에 자동으로 적용됩니다.
- Zscaler 포털에서 직접 볼 수 있는 200개의 선도적인 클라우드 앱에서 Cloud App Security의 위험 평가를 사용하여 Zscaler 포털을 개선합니다.

## <a name="prerequisites"></a>필수 구성 요소

- Microsoft Cloud App Security에 대한 유효한 라이선스
- Zscaler Cloud 5.6에 대한 유효한 라이선스
- 활성 Zscaler NSS 구독 

## <a name="deployment"></a>배포

1. Zscaler 포털에서 [Microsoft Cloud App Security와 Zscaler 파트너 통합](https://help.zscaler.com/zia/configuring-mcas-integration)을 완료하기 위한 단계를 수행하세요.
2. Cloud App Security 포털에서 다음 통합 단계를 수행하세요.
    1. 설정 코그를 클릭하고 **Cloud Discovery Settings**(Cloud Discovery 설정)를 선택합니다. 
    2. **Automatic log upload**(자동 로그 업로드) 탭을 클릭한 다음, **Add data source**(데이터 원본 추가)를 클릭합니다.
    3. **Add data source**(데이터 원본 추가) 페이지에서 다음 설정을 입력합니다.

       - Name(이름) = NSS
       - Source(원본) = Zscaler QRadar LEEF
       - Receiver type(수신기 유형) = Syslog - UDP

         ![데이터 원본 Zscaler](./media/data-source-zscaler.png)

    4. **View sample of expected log file**(필요한 로그 파일의 샘플 보기)을 클릭합니다. 그런 다음, **Download sample log**(샘플 로그 다운로드)를 클릭하여 샘플 검색 로그를 보고 해당 로그와 일치하는지 확인합니다.<br>

3. 네트워크에서 검색된 클라우드 앱을 조사합니다. 자세한 정보 및 조사 단계는 [Cloud Discovery 작업](working-with-cloud-discovery-data.md)을 참조하세요.

4. Cloud App Security에서 비사용 권한으로 설정한 모든 앱에는 Zscaler에 의해 두 시간마다 ping이 사용된 다음, 해당 앱은 Zscaler에 의해 자동으로 차단됩니다. 앱 사용 권한 취소에 대한 자세한 내용은 [앱 사용 권한 부여/취소](governance-discovery.md#BKMK_SanctionApp)를 참조하세요.

## <a name="next-steps"></a>다음 단계

[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  