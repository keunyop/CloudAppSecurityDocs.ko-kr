---
title: Cloud App Security와 iboss 통합
description: 이 문서에서는 원활한 Cloud Discovery 및 승인되지 않은 앱의 자동 차단을 위해 Microsoft Cloud App Security와 iboss 보안 클라우드 게이트웨이를 통합하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/2/2019
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 920d4272-685b-4c4d-9b31-94a2c6f3503e
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 34d92504322b4210cf4a129b3392fd8e3de15050
ms.sourcegitcommit: 7b1b1e80f90bd12e38a2e14dfea6708341eb0f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "55668971"
---
# <a name="integrate-cloud-app-security-with-iboss"></a>Cloud App Security와 iboss 통합

*적용 대상: Microsoft Cloud App Security*

Cloud App Security와 iboss를 모두 사용하는 경우 두 제품을 통합하여 보안 Cloud Discovery 환경을 향상할 수 있습니다. iboss는 조직의 트래픽을 모니터링하고 트랜잭션을 차단하는 정책을 설정할 수 있는 독립 실행형 보안 클라우드 게이트웨이입니다. Cloud App Security와 iboss는 함께 다음 기능을 제공합니다.

- Cloud Discovery의 원활한 배포 - iboss를 사용하여 트래픽을 프록시하고 Cloud App Security로 보냅니다. 이를 통해 Cloud Discovery를 사용하기 위해 네트워크 엔드포인트에 로그 수집기를 설치할 필요가 없습니다.
- iboss의 차단 기능은 Cloud App Security에서 비사용 권한으로 설정한 앱에 자동으로 적용됩니다.
- iboss 관리 포털에서 직접 볼 수 있는 조직의 상위 100개 클라우드 앱에 대한 Cloud App Security의 위험 평가를 통해 iboss 관리 포털을 개선합니다.

## <a name="prerequisites"></a>필수 구성 요소

- Microsoft Cloud App Security에 대한 유효한 라이선스
- iboss 보안 클라우드 게이트웨이에 대한 유효한 라이선스(9.1.100.0 이상 릴리스)

## <a name="deployment"></a>배포

1. Cloud App Security 포털에서 다음 통합 단계를 수행합니다.
    1. 설정 코그를 클릭하고 **Cloud Discovery 설정**을 선택합니다. 
    2. **자동 로그 업로드** 탭을 선택한 다음, **데이터 원본 추가**를 선택합니다.
    3. **Add data source**(데이터 원본 추가) 페이지에서 다음 설정을 입력합니다.

       - 이름 = iboss
       - 원본 = iboss Secure Cloud Gateway
       - Receiver type(수신기 유형) = Syslog - UDP

         ![데이터 원본 iboss](./media/iboss-integration.png)

    4. **View sample of expected log file**(필요한 로그 파일의 샘플 보기)을 클릭합니다. 그런 다음, **Download sample log**(샘플 로그 다운로드)를 클릭하여 샘플 검색 로그를 보고 해당 로그와 일치하는지 확인합니다.<br>

3. 네트워크에서 검색된 클라우드 앱을 조사합니다. 자세한 정보 및 조사 단계는 [Cloud Discovery 작업](working-with-cloud-discovery-data.md)을 참조하세요.

4. Cloud App Security에서 비사용 권한으로 설정한 모든 앱은 10분마다 한 번씩 iboss에 의해 ping이 사용된 다음, iboss에 의해 자동으로 차단됩니다. 앱 사용 권한 취소에 대한 자세한 내용은 [앱 사용 권한 부여/취소](governance-discovery.md#BKMK_SanctionApp)를 참조하세요.

5. 트래픽 로그를 Microsoft Cloud App Security로 보내도록 iboss를 구성하려면 iboss 지원팀에 문의하세요.

## <a name="next-steps"></a>다음 단계

[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  