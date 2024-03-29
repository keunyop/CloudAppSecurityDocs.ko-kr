---
title: 위험한 OAuth 앱 조사 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud App Security에서 위험한 OAuth 앱을 조사하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 04/08/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4118681e-362f-4b10-aa08-39691aa7800a
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: d2972f43725cdd6e9ea70ce305f41c11a621960b
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568312"
---
# <a name="tutorial-investigate-risky-oauth-apps"></a>자습서: 위험한 OAuth 앱 조사

*적용 대상: Microsoft Cloud App Security*

OAuth는 토큰 기반 인증 및 권한 부여를 위한 개방형 표준입니다. OAuth를 통해 사용자의 암호를 노출하지 않고 타사 서비스가 사용자의 계정 정보를 사용할 수 있습니다. OAuth는 사용자를 대신하여 중개자로 작동하며 공유할 특정 계정 정보에 권한을 부여하는 액세스 토큰과 함께 서비스를 제공합니다. 

예를 들어 사용자의 일정을 분석하고 생산성을 높이는 방법에 대한 조언을 제공하는 앱은 사용자의 일정에 액세스해야 합니다. 사용자의 자격 증명을 제공하는 대신 OAuth를 사용하면 아래 그림과 같이 사용자가 페이지에 동의할 때 생성되는 토큰에만 기반하여 데이터에 액세스할 수 있습니다.

 ![OAuth 앱 권한](./media/oauth-permission.png) 

조직의 비즈니스 사용자가 설치하는 타사 앱 중에는 사용자 정보와 데이터의 사용 권한을 요청하고 사용자 대신 다른 클라우드 앱에 로그인하는 것도 많습니다. 사용자가 이러한 앱을 설치할 때, 응용 프로그램에 사용 권한을 부여하는 내용을 포함한 메시지의 세부 정보를 검토하지 않고 **허용**을 클릭하는 경우도 많습니다. 타사 앱 권한을 수락하면 조직에 보안 위험이 발생할 수 있습니다.

예를 들어 다음 OAuth 앱 승인 페이지는 일반적인 사용자에게 적합하게 보일 수 있지만 “Google APIs Explorer”는 Google 자체의 권한을 요청할 필요가 없습니다. 따라서 이것은 앱이 피싱 시도일 수 있으며 Google과 전혀 관련이 없음을 나타냅니다.

 ![OAuth 피싱](./media/oauth-phishing.png) 

보안 관리자는 자신의 환경에 있는 앱을 보고 제어할 수 있어야 하며 여기에는 앱에 따른 권한이 있어야 합니다. 또한 취소하려는 리소스에 대한 권한이 필요한 앱의 사용을 차단할 수 있어야 합니다. 따라서 Microsoft Cloud App Security에서는 사용자가 부여한 앱 권한을 조사하고 모니터링할 수 있는 기능을 제공합니다. 이 문서는 조직에서 OAuth 앱을 조사하고 더 의심스러운 앱에 집중할 수 있도록 지원하기 위한 목적으로 작성되었습니다. 

Microsoft는 Cloud App Security 포털에서 제공된 기능 및 정보를 사용하여 조사를 실시하는 방식으로 위험 가능성이 낮은 앱을 필터링하고 의심스러운 앱에 집중하는 것을 권장합니다. 

## <a name="how-to-detect-risky-oauth-apps"></a>위험한 OAuth 앱을 찾는 방법

위험한 OAuth 앱 감지는 다음 기능을 사용하여 수행할 수 있습니다. 

- **경고**: 기존 정책에 의해 트리거된 경고에 응답합니다. 
- **헌팅**: 구체적인 위험 혐의 없이 사용 가능한 모든 앱 중에서 위험한 앱을 검색합니다. 


### <a name="detect-risky-apps-using-alerts"></a>경고를 사용하여 위험한 앱 감지

OAuth 앱이 특정 기준을 충족하면 자동으로 알림이 전송되도록 정책을 설정할 수 있습니다. 예를 들어, 높은 권한이 필요하고 50명 이상의 사용자가 인증한 앱이 감지되면 자동으로 알려주도록 정책을 설정할 수 있습니다. OAuth 정책을 만드는 방법에 대한 자세한 내용은 [OAuth 앱 정책](app-permission-policy.md)을 참조하세요.

### <a name="detect-risky-apps-by-hunting"></a>헌팅을 통해 위험한 앱 감지

1.  포털에서 **조사**로 이동한 다음 **OAuth 앱**으로 이동합니다. 필터 및 쿼리를 사용하여 사용자 환경에서 발생하는 문제를 검토하세요.

    - 필터를 **권한 수준 높은 심각도**와 **커뮤니티 사용 일반적이지 않음**으로 설정합니다. 필터를 사용하여 매우 위험할 수 있고 사용자가 해당 위험을 과소 평가할 수 있는 앱에 집중할 수 있습니다.
    - **권한**에서 특정 상황에서 특히 위험한 모든 옵션을 선택합니다. 예를 들어 메일 액세스 권한(예: **모든 사서함에 대한 모든 권한**)을 제공하는 모든 필터를 선택한 다음 앱 목록을 검토하여 해당 앱에 모두 메일 관련 액세스가 실제로 필요한지 확인할 수 있습니다. 이 작업을 통해 특정 컨텍스트 내에서 조사를 진행하고, 적절해 보이나 불필요한 권한이 포함된 앱을 찾을 수 있습니다. 이러한 앱이 위험할 가능성이 더 높습니다. 
    
      ![OAuth 피싱](./media/oauth-filters.png) 
 
    - 저장된 쿼리 **외부 사용자가 승인한 앱**합니다. 이 필터를 사용하면 회사의 보안 규정을 준수하지 않는 것으로 보이는 앱을 찾을 수 있습니다.
2.  앱을 검토한 후 합법적으로 보이나 실제로는 위험한 앱을 쿼리에서 집중할 수 있습니다. 이러한 앱을 찾으려면 필터를 사용하세요.
    - **적은 수의 사용자가 권한을 부여한** 앱을 필터링하세요. 이 앱에 집중하면 손상된 사용자가 권한을 부여한 위험한 앱을 찾을 수 있습니다.
    - 앱의 목적과 일치하지 않는 권한을 보유한 앱(예: 모든 사서함에 대한 모든 권한을 보유한 시계 앱).
3. 각 앱을 클릭하여 앱 서랍을 열고 앱에 의심스러운 이름, 게시자 또는 웹 사이트가 있는지 확인하세요.
1. **마지막으로 권한을 부여한 날짜**가 최근이 아닌 앱 및 대상 앱의 목록을 확인하세요. 이 앱은 더 이상 필요하지 않습니다. 

   ![OAuth 앱 서랍](./media/oauth-drawer.png) 


## <a name="how-to-investigate"></a>조사 방법

앱이 의심스럽고 조사가 필요하다고 판단되면 효율적인 조사를 위해 다음과 같은 주요 원칙을 권장합니다. 

- 조직에 의해 또는 온라인으로 더 일반적이고 자주 사용되는 앱일수록 더 안전할 수 있습니다.
- 앱은 앱의 목적과 관련된 권한만 요구해야 합니다. 그렇지 않다면 그 앱은 위험할 수 있습니다. 
- 높은 권한이나 관리자 동의를 요구하는 앱은 위험할 수 있습니다. 


1. 앱을 클릭하여 앱 서랍을 열고 **관련 활동**에 있는 링크를 클릭하세요. 이 링크를 클릭하면 앱이 수행한 활동을 필터링하는 활동 로그 페이지가 열립니다. 일부 앱의 경우 사용자가 수행하는 것으로 등록된 활동을 수행합니다. 이 활동은 활동 로그에서 자동으로 필터링으로 제외됩니다. 활동 로그를 사용하여 더 자세히 조사하려면 [활동 로그](activity-filters.md)를 참조하세요. 
4. 앱이 의심스러워 보이는 경우 다른 앱 스토어에서 앱 이름과 게시자를 조사하는 것이 좋습니다. 의심스러운 다음 앱에 집중하세요. 
    - 다운로드 수가 적은 앱.
    - 등급 또는 점수가 낮거나 좋지 않은 의견이 달린 앱.
    - 게시자 또는 웹 사이트가 의심스러운 앱.
    - 마지막 업데이트가 최신이 아닌 앱. 앱이 더 이상 지원되지 않음을 나타낼 수 있습니다. 
    - 관련 없는 권한을 보유한 앱. 위험한 앱임을 나타낼 수 있습니다. 
5. 앱이 여전히 의심스러운 경우 온라인에서 앱 이름, 게시자, URL을 조사할 수 있습니다. 

## <a name="how-to-remediate"></a>해결 방법 

OAuth 앱이 위험하다고 판단되면 Cloud App Security에서는 다음과 같은 해결 옵션을 제공합니다. 

- **수동 해결 방법**: [OAuth 앱 페이지에서 앱을 취소 및 금지](manage-app-permissions.md#ban-or-approve-an-app)할 수 있습니다.

- **자동 해결 방법**: [자동으로 앱을 취소하거나 앱에서 특정 사용자를 취소](app-permission-policy.md)하는 정책을 만들 수 있습니다.


 
## <a name="next-steps"></a>다음 단계
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md) 

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/) 
 
