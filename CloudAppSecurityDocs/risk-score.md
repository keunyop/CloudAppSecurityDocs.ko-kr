---
title: "위험 점수 사용 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security 앱 위험 점수를 사용하고 사용자 지정하는 방법에 관한 지침을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/2/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9cb3594e-5007-48be-9b4f-e1d23355d86e
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 2fcc085cc53d2d7580640022029b1a528bea416a
ms.sourcegitcommit: 661f4ce41262e8462c90fd2a4f1232e2154d5113
translationtype: HT
---
# <a name="working-with-the-risk-score"></a>위험 점수 사용  

## <a name="the-cloud-app-catalog"></a>클라우드 앱 카탈로그

Cloud App Security의 Cloud Discovery에서 검색할 수 있는 클라우드 앱을 더 적절히 이해하려면 클라우드 앱 카탈로그를 사용하세요.

클라우드 앱 카탈로그에는 이름, 도메인, 위험 점수, 범주 또는 사용 가능한 보안 기능에 따라 표시(필터링)할 수 있는 14,000개 이상의 SaaS 응용 프로그램이 포함되어 있습니다.

![클라우드 앱 카탈로그에 액세스](./media/risk-cac-dropdown.png)

## <a name="discovery-requests"></a>검색 요청

클라우드 앱 카탈로그의 정보 및 위험 점수는 다양한 소스를 기반으로 합니다. Microsoft는 정보를 최신 상태로 유지하기 위해 최선을 다하고 있지만, 모든 데이터 원본의 정확도를 보증하지는 않습니다. 

앱에 대한 정보가 오래되었다고 생각하는 경우 문의해 주세요.

-    점수 업데이트 요청 - 당사 팀이 클라우드 앱을 다시 평가하기를 원하는 경우
-    새 데이터 보고(특정 필드별로 또는 일반에 대해) - 앱에 대한 정보가 오래되었다고 생각하는 경우

![위험 데이터 업데이트](./media/risk-cac-feedback.png)

또한 Cloud Discovery에서 조직이 사용하는 클라우드 앱을 현재 검색할 수 없는 경우 해당 앱의 추가를 제안하는 것이 좋습니다.

![새 앱 제안](./media/risk-suggest-app.png)


## <a name="customizing-the-risk-score"></a>위험 점수 사용자 지정

Cloud Discovery는 환경에서 사용되는 클라우드 앱의 신뢰도 및 안정성과 관련해서 중요한 데이터를 제공합니다. 포털 내에서 검색된 각 앱은 엔터프라이즈의 이 특정 앱 사용 성숙도에 대한 Cloud App Security의 평가를 나타내는 총점과 함께 표시됩니다. 지정된 모든 앱의 총점은 Cloud App Security에서 안정성을 평가할 때 고려하는 다음 세 가지 하위 범주와 관련된 하위 점수 3개의 가중 평균입니다.  
  
-   **일반** - 이 범주는 도메인, 창립 연도, 인기도 등 앱을 생산하는 회사에 대한 기본 사항을 가리킵니다. 이러한 필드는 가장 기본적인 수준에서 회사의 안정성을 나타냅니다.  
  
-   **보안** - 보안 범주는 검색된 앱이 활용하는 데이터의 물리적 보안을 다루는 모든 표준을 고려합니다. 여기에는 다단계 인증, 암호화, 데이터 분류, 데이터 소유권 등의 필드가 포함됩니다.  
  
-   **규정 준수** - 이 범주는 앱을 생산하는 회사에서 유지하는 일반적인 모범 사례 규정 준수 표준을 표시합니다. 사양 목록에는 HIPAA, CSA, PCI-DSS 등의 표준이 포함됩니다.  
  
각 범주는 많은 특정 속성으로 구성됩니다. 점수 매기기 알고리즘에 따라 각 속성은 값을 기준으로 0과 10 사이의 예비 점수를 받습니다. True/False 값은 각각 10 또는 0을 받지만 도메인 사용 기간 등의 연속 속성은 스펙트럼 내의 특정 값을 받게 됩니다. 각 속성의 점수는 범주의 하위 점수를 만들기 위해 범주의 다른 모든 기존 필드를 기준으로 가중 처리됩니다. 점수가 없는 앱을 발견할 경우 일반적으로 속성을 알 수 없어 점수가 매겨지지 않은 앱을 나타냅니다.  
  
클라우드 검색 점수 구성에 제공된 기본 가중치를 잠시 검토하고 수정하는 것이 중요합니다. 기본적으로 평가된 모든 매개 변수에 동일한 가중치가 지정됩니다. 조직에 더 중요하거나 덜 중요한 특정 매개 변수가 있는 경우 다음과 같이 변경하는 것이 중요합니다.  
  
1.  포털의 설정 아이콘에서 **클라우드 검색 설정**을 선택합니다.  
  
2.  **점수 메트릭 구성**에서 **중요도**를 밀어 필드 또는 위험 범주의 가중치를 **무시됨**, **낮음**, **중간**, **높음** 또는 **매우 높음**으로 변경합니다.  
  
3.  또한 점수를 계산할 때 특정 값을 사용할 수 없거나 적용할 수 없는지 여부를 설정할 수 있습니다. 포함할 경우 해당 없음 값에는 점수에 대한 음의 기여도가 포함됩니다.  
  
     ![점수](./media/score.png "점수")  

위험 점수가 누적되는 방식을 이해하는 데 필요한 모든 정보는 Cloud App Security 포털에서 확인할 수 있습니다.
특정 위험 범주 내 위험 요인의 가중치를 더 적절히 이해하려면 앱 프로필의 각 필드 이름 오른쪽에 있는 "i" 단추를 사용해 보세요. 그러면 Cloud App Security에서 특정 위험 요인을 정확하게 채점하는 방식에 대한 정보를 확인할 수 있습니다. 점수는 1-10점 척도 + 위험 범주의 가중치를 통해 계산된 위험 요인의 값입니다.

![위험 계산](./media/cac-weight.png)
  
앱의 총점에 반영된 위험 범주의 가중치를 더 적절히 이해하려면 위험 범주 점수를 마우스로 가리킵니다.

![위험 범주 가중치](./media/risk-category-weight.png)


 
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  