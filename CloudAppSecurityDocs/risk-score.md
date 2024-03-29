---
title: 위험 점수 사용 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud App Security 앱 위험 점수를 사용하고 사용자 지정하는 방법에 관한 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 1/27/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9cb3594e-5007-48be-9b4f-e1d23355d86e
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: b6f158408422a8b04dbabefe089d30b464ac4ac3
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568582"
---
# <a name="working-with-the-risk-score"></a>위험 점수 사용

*적용 대상: Microsoft Cloud App Security*

클라우드 앱 카탈로그를 통해 Cloud Discovery가 무엇을 나타내는지 전체적으로 파악할 수 있습니다. Cloud Discovery는 16,000개 이상의 클라우드 앱이 포함된 Microsoft Cloud App Security 클라우드 앱 카탈로그에 대한 트래픽 로그를 분석합니다. 이 앱은 70개를 넘는 위험 요인을 기준으로 순위 및 점수를 매겨 클라우드 사용, 섀도 IT 및 섀도 IT가 조직에 미치는 위험에 대한 지속적인 가시성을 제공합니다. 이 문서에서는 Cloud App Security 앱 위험 점수를 사용하고 사용자 지정하는 방법에 관한 지침을 제공합니다.

## <a name="the-cloud-app-catalog"></a>클라우드 앱 카탈로그

**클라우드 앱 카탈로그**는 규정 인증, 산업 표준 및 모범 사례에 따라 클라우드 앱의 위험을 평가합니다. 클라우드 앱 카탈로그에서 네 개의 보완 프로세스를 실행하여 다음 항목에 대한 최신 정보를 제공합니다.
1. 클라우드 앱에서 직접 자동화된 데이터를 추출합니다. 추출은 SOC 2 규정 준수, 서비스 약관, 로그온 URL, 개인정보처리방침 및 HQ 위치와 같은 특성에 대한 것입니다.
2. Cloud App Security의 알고리즘에 따라 데이터에 대한 자동화된 고급 데이터 추출(HTTP 보안 헤더와 같은 특성)
3. Cloud App Security 클라우드 분석가 팀에 의한 연속 분석(미사용 암호화 같은 특성)
4. 클라우드 앱 카탈로그의 변경 내용에 대한 고객 제출 요청에 따른 고객 기반 수정 요청. 모든 요청은 클라우드 분석가 팀에서 검토하고 해당 결과에 따라 업데이트됩니다.
  
![클라우드 앱 카탈로그](./media/cloud-app-catalog.png)  

변화하는 필요에 대한 해결 방법으로 비즈니스 단위의 클라우드 앱 수요가 증가하고 있습니다. 클라우드 앱 카탈로그를 사용하면 조직의 보안 요구 사항에 맞는 앱을 현명하게 선택할 수 있습니다. 카탈로그는 최신 보안 표준, 취약성 및 위반 사항을 최신 상태로 유지합니다.

예를 들어 CRM 앱을 비교하여 적절하게 보호되고 있는지 확인합니다. 클라우드 앱 카탈로그 페이지를 사용하여 원하는 관련 앱을 필터링할 수 있습니다.

1. **클라우드 앱 카탈로그** 페이지의 **범주별로 찾아보기**에서 **CRM**을 선택합니다. 
2. **고급 필터**를 사용하여 **SOC 2**에 대한 **위험 요인 준수**를 **True**로 설정합니다.
3. **ISO 27001**에 대한 **위험 요인 준수**를 **True**로 설정합니다.
4. **미사용 데이터 암호화**에 대한 **보안 위험 요인**을 **지원되지 않음** 및 **N/A**와 동일하지 않게 설정합니다.
5. **관리 감사 내역**에 대한 **보안 위험 요인**을 **True**로 설정합니다.
6. **사용자 감사 내역**에 대한 **보안 위험 요인**을 **True**로 선택합니다.

![클라우드 앱 카탈로그 필터](./media/cloud-app-catalog-filters.png)

결과가 필터링된 후 관련 앱을 검토하고 필요에 가장 잘 맞는 앱을 찾을 수 있습니다.

## <a name="cloud-app-catalog-filters"></a>클라우드 앱 카탈로그 필터

기본 및 고급 클라우드 앱 카탈로그 필터가 있습니다. 복잡한 필터를 빌드하려면 다음 필터가 모두 포함된 고급 옵션을 사용합니다.

- **앱 태그**: 태그를 사용하여 클라우드 앱 카탈로그를 사용자 지정할 수 있습니다. 
  **사용 권한** 또는 **미사용 권한** 중에서 선택하거나 앱의 사용자 지정 태그를 만들 수 있습니다. 이러한 태그는 필터로 사용할 수 있습니다. 필터는 조사하려는 앱의 특정 유형을 심층 분석하는 데 유용합니다. 
- **앱 및 도메인**: 특정 앱 또는 특정 도메인에서 사용되는 앱을 검색할 수 있습니다. 
- **범주**: 페이지 왼쪽에 있는 범주 필터를 사용하여 앱 범주에 따라 앱 유형을 검색할 수 있습니다. 예: 소셜 네트워크 앱, 클라우드 스토리지 앱 및 더 다양한 유형의 앱. 한 번에 둘 이상의 범주를 선택하거나 단일 범주를 선택할 수 있습니다. 그런 다음, 범주 상단에 기본 또는 고급 필터를 적용합니다.
- **위험 요인 규정 준수**: 앱이 준수할 수 있는 특정 표준, 인증 및 규정 준수를 검색할 수 있습니다. 예로는 HIPAA, ISO 27001, SOC 2 및 PCI-DSS가 있습니다.
- **일반 위험 요인**: 소비자 인기도, 데이터 센터 로캘 등의 일반 위험 요인을 검색할 수 있습니다.
- **법적 위험 요소**: 준비된 모든 규정 및 정책에 따라 필터링할 수 있습니다. 법적 위험 요소를 사용하면 GDPR, DMCA 및 데이터 보존 정책과 같은 앱 사용자의 데이터 보호 및 개인 정보 보호가 보장됩니다.
- **위험 점수**: 집중할 수 있는 위험 점수를 기준으로 앱을 필터링합니다. 예를 들어 위험한 앱만 검토합니다.
- **보안 위험 요인**: 특정 보안 조치에 따라 필터링할 수 있습니다. 측정값에는 미사용 암호화, 다단계 인증 및 기타가 포함됩니다.

## <a name="suggesting-a-change"></a>변경 제안

Cloud App Security에서 점수를 매기지 않은 새 앱을 사용자 환경에서 찾은 경우 앱 검토를 요청할 수 있습니다. 또한 새 위험 요인, 점수 업데이트 또는 오래된 앱 데이터에 대한 검토를 요청할 수 있습니다.

**새 앱을 제안하려면:**

1. **검색된 앱** 페이지의 맨 위에서 점 세 개를 클릭하고 **새 앱 제안**을 선택합니다.

   ![Cloud App Security에 대한 앱 제안](./media/suggest-new-app.png)

2. **새 클라우드 앱 제안** 팝업에서 새 항목에 대한 세부 정보를 입력합니다. 앱의 이름과 도메인을 포함합니다.

   ![Cloud App Security에 대한 앱 팝업 제안](./media/suggest-new-app-popup.png)

3. 앱에 대한 추가 정보가 필요한 경우 Cloud App Security 분석가가 연락할 수 있는 확인란을 선택하는 것이 좋습니다. 연락처 정보를 입력하면 분석이 완료될 때 업데이트할 수 있습니다.

**위험 요인, 점수 또는 앱 데이터를 업데이트하려면:**

1. **클라우드 앱 카탈로그** 페이지의 업데이트할 앱 행에서 행 끝에 있는 점 세 개를 클릭하고 **점수 업데이트 요청**을 선택합니다.

   ![점수 업데이트 요청](./media/request-score-update.png)

2. **개선 사항 제안** 팝업에서 점수 업데이트를 요청하건, 새 위험 요인을 제안하거나, 앱 데이터를 업데이트할지 선택합니다.

   ![Cloud App Security에 대한 개선 사항 제안](./media/suggest-improvement-popup.png)

3. 앱에 대한 추가 정보가 필요한 경우 Cloud App Security 분석가가 연락할 수 있는 확인란을 선택하는 것이 좋습니다. 연락처 정보를 입력하면 분석이 완료될 때 업데이트할 수 있습니다.
 
## <a name="customizing-the-risk-score"></a>위험 점수 사용자 지정

Cloud Discovery는 환경에서 사용되는 클라우드 앱의 신뢰도 및 안정성과 관련해서 중요한 데이터를 제공합니다. 포털 내에서 검색된 각 앱은 총점과 함께 표시됩니다. 점수는 이 특정 앱의 엔터프라이즈용 사용 성숙도에 대한 Cloud App Security의 평가를 나타냅니다. 지정된 모든 앱의 총점은 Cloud App Security에서 안정성을 평가할 때 고려하는 다음 세 가지 하위 범주와 관련된 하위 점수 3개의 가중 평균입니다.  
  
- **일반** - 이 범주는 도메인, 창립 연도, 인기도 등 앱을 생산하는 회사에 대한 기본 사항을 가리킵니다. 이러한 필드는 가장 기본적인 수준에서 회사의 안정성을 표시하기 위한 것입니다.  
  
- **보안** - 보안 범주는 검색된 앱이 사용하는 데이터의 물리적 보안을 다루는 모든 표준을 설명합니다. 이 범주에는 다단계 인증, 암호화, 데이터 분류, 데이터 소유권 등의 필드가 포함됩니다.  
  
- **규정 준수** - 이 범주는 앱을 생산하는 회사에서 유지하는 일반적인 모범 사례 규정 준수 표준을 표시합니다. 사양 목록에는 HIPAA, CSA, PCI-DSS 등의 표준이 포함됩니다.  

- **법적**: 이 범주는 데이터 보호와 앱 사용자의 개인 정보 보호를 위해 보호하기 위해 확립된 규정(GDPR, DMCA, 데이터 보존 정책 등) 중 어느 것이 어느 앱에 적용되어 있는지 표시합니다.
  
각 범주는 많은 특정 속성으로 구성됩니다. Cloud App Security 점수 매기기 알고리즘에 따라 각 속성은 값을 기준으로 0과 10 사이의 예비 점수를 받습니다. True/False 값은 각각 10 또는 0을 받게 됩니다. 그러나 도메인 사용 기간 등의 연속 속성은 스펙트럼 내의 특정 값을 받게 됩니다. 각 속성의 점수는 범주의 하위 점수를 만들기 위해 범주의 다른 모든 기존 필드를 기준으로 가중 처리됩니다. 점수가 없는 앱을 발견할 경우 일반적으로 속성을 알 수 없어 점수가 매겨지지 않은 앱을 나타냅니다.  
  
클라우드 검색 점수 구성에 제공된 기본 가중치를 잠시 검토하고 수정하는 것이 중요합니다. 기본적으로 평가된 모든 매개 변수에 동일한 가중치가 지정됩니다. 조직에 더 중요하거나 덜 중요한 특정 매개 변수가 있는 경우 다음과 같이 변경하는 것이 중요합니다.  
  
1. 포털의 설정 아이콘에서 **클라우드 검색 설정**을 선택합니다.  
  
2. **점수 메트릭**에서 **중요도**를 슬라이드하여 필드 또는 위험 범주의 가중치를 변경합니다. 중요도는 **무시**, **낮음**, **중간**, **높음** 또는 **매우 높음**으로 설정할 수 있습니다.  
  
3. 또한 점수를 계산할 때 특정 값을 사용할 수 없거나 적용할 수 없는지 여부를 설정할 수 있습니다. 포함할 경우 해당 없음 값에는 점수에 대한 음의 기여도가 포함됩니다.  
  
   ![점수](./media/score.png "점수 메트릭")  

Cloud App Security 위험 점수가 누적되는 방식을 이해하는 데 필요한 모든 정보는 Cloud App Security 포털에서 확인할 수 있습니다. 특정 위험 범주 내 위험 요인의 가중치를 더 적절히 이해하려면 앱 프로필의 각 필드 이름 오른쪽에 있는 "i" 단추를 사용해 보세요. 그러면 Cloud App Security에서 특정 위험 요인을 정확하게 채점하는 방식에 대한 정보를 확인할 수 있습니다. 점수는 1-10점 척도 + 위험 범주의 가중치를 통해 계산된 위험 요인의 값입니다.

![위험 계산](./media/cac-weight.png)
  
앱의 총점에 반영된 위험 범주의 가중치를 더 적절히 이해하려면 위험 범주 점수를 마우스로 가리킵니다.

![위험 범주 가중치](./media/risk-category-weight.png)

## <a name="overriding-the-risk-score"></a>위험 점수 재정의


위험 점수를 재정의하려면 **검색된 앱** 테이블 또는 **클라우드 앱 카탈로그**에서 앱 오른쪽에 있는 점 세 개를 클릭하고 **앱 점수 재정의**를 선택합니다.
조직에 대한 즉각적인 결과를 얻도록 가중치가 적용된 방식을 변경하지 않고 앱의 위험 점수를 재정의할 수 있습니다. 예를 들어 사용하는 LOB 앱의 위험 점수는 8입니다. 그러나 앱은 조직에서 승인되어 권장됩니다. LOB 앱의 위험 점수를 10으로 변경할 수 있습니다.
![Cloud App Security 앱 위험 점수 재정의](./media/override-risk-score.png)

점수를 업데이트한 후 앱 메모를 포함하여 이 앱 점수를 수정하기 위한 비즈니스 근거를 다른 관리자에게 분명하게 설명할 수 있습니다. 

메모를 추가하여 누군가 앱을 검토할 때 변경의 근거를 분명히 설명할 수도 있습니다.


 
## <a name="next-steps"></a>다음 단계
 
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
