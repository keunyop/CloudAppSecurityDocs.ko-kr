---
title: 위험한 OAuth 앱 조사 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud App Security에서 위험한 OAuth 앱을 조사하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 3/17/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4118681e-362f-4b10-aa08-39691aa7800a
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 77b33d524e3a88d49c4dd2bcd71bc31c0fa26250
ms.sourcegitcommit: 57bad4dc9b28326c93ee480d308d52ea23c42089
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "58163660"
---
# <a name="investigate-risky-oauth-apps"></a>위험한 OAuth 앱 조사

*적용 대상: Microsoft Cloud App Security*

OAuth는 토큰 기반 인증 및 권한 부여를 위한 개방형 표준입니다. OAuth를 통해 사용자의 암호를 노출하지 않고 타사 서비스가 사용자의 계정 정보를 사용할 수 있습니다. OAuth는 사용자를 대신하여 중개자로 작동하며 공유할 특정 계정 정보에 권한을 부여하는 액세스 토큰과 함께 서비스를 제공합니다.

조직의 비즈니스 사용자가 설치하는 타사 앱 중에는 사용자 정보와 데이터의 사용 권한을 요청하고 사용자 대신 다른 클라우드 앱에 로그인하는 것도 많습니다. 사용자가 이러한 앱을 설치할 때, 응용 프로그램에 사용 권한을 부여하는 내용을 포함한 메시지의 세부 정보를 검토하지 않고 **허용**을 클릭하는 경우도 많습니다.

타사 앱 권한을 수락하면 조직에 잠재적인 보안 위험을 가져올 수 있으므로 Microsoft Cloud App Security에서 사용자가 부여한 앱 권한을 조사하고 모니터링할 수 있는 기능을 제공합니다. 이 문서는 조직에서 OAuth 앱을 조사하고 더 의심스러운 앱에 집중할 수 있도록 지원하기 위한 목적으로 작성되었습니다. 

Microsoft는 Cloud App Security 포털에서 제공된 기능 및 정보를 사용하여 조사를 실시하는 방식으로 위험 가능성이 낮은 앱을 필터링하고 의심스러운 앱에 집중하는 것을 권장합니다. 

## <a name="how-to-investigate"></a>조사 방법 

1.  포털에서 필터를 사용하는 연결된 모든 OAuth 앱 쿼리 중 권장되는 필터 및 쿼리는 다음과 같습니다. 
    1. 높은 권한 수준 및 일반적이지 않은 커뮤니티 사용 이 필터를 사용하면 사용자가 위험을 파악하지 못할 가능성이 있는 잠재적으로 위험 수준이 높은 앱에 집중할 수 있습니다. 
    2. 특정 앱 유형과 관련된 특정 위험 권한(예: 모든 사서함에 대한 모든 권한을 보유한 앱) 이 필터를 사용하면 특정 컨텍스트를 조사할 수 있으며, 이를 통해 합법적인 것으로 보이나 무관한 권한을 포함한 앱을 찾을 수 있습니다. 해당 앱이 악성일 가능성이 더 높습니다. 
    3. 외부 사용자가 승인한 앱 이 필터를 사용하면 회사의 보안 규정을 준수하지 않는 것으로 보이는 앱을 찾을 수 있습니다. 
2.  의심스러운 다음 앱에 집중하세요. 
    1. “권한을 부여한 사용자” 수가 적은 앱 이 앱에 집중하면 손상된 사용자가 권한을 부여한 악성 앱을 찾을 수 있습니다. 
    2. 앱의 목적에 부합하지 않는 권한을 보유한 앱(예: 모든 사서함에 대한 모든 권한을 보유한 시계 앱) 이 앱에 집중하면 합법적으로 보이나 실제로는 악성인 앱을 찾을 수 있습니다. 
    3. 이름, 게시자 또는 웹 사이트가 의심스러운 앱 이 앱에 집중하면 의심스러운 앱을 빠르게 찾을 수 있습니다. 
    4. “마지막으로 권한을 부여한 날짜”가 오래된 앱 이 앱에 집중하면 더 이상 필요하지 않은 앱을 찾을 수 있습니다. 
3. 관련 활동 링크를 사용하여 활동 로그 페이지에서 앱으로 수행된 활동을 확인합니다. 이를 통해 사용자와 앱 이름이 같은 활동을 분류하는 필터가 자동으로 생성됩니다. 그러나 일부 앱은 사용자 중 하나로서 활동을 수행할 수 있습니다. 해당 이벤트는 활동 로그에서 이용할 수 있으나 필터링될 수 있습니다. 
4. 앱이 의심스러워 보이는 경우 다른 앱 스토어에서 앱 이름과 게시자를 확인하는 것이 좋습니다. 의심스러운 다음 앱에 집중하세요. 
    1. 다운로드 수가 적은 앱
    2. 점수가 낮거나 좋지 않은 의견이 달린 앱
    3. 게시자 또는 웹 사이트가 의심스러운 앱
    4. 더 이상 지원되지 않음을 앱에서 알 수 있는 마지막 업데이트 날짜가 오래된 앱 
    5. 권한에 부합하지 않아 앱이 악성임을 알 수 있는 앱 
5. 앱이 여전히 의심스러운 경우 온라인에서 앱 이름 게시자와 URL을 검색할 수 있습니다. 

## <a name="example"></a>예제 

조사 아이콘에서 “OAuth 앱” 옵션 선택
 
필터 옵션을 사용하여 앱 필터링(1단계와 동일)
 

포털에서 사용 가능한 정보를 활용하여 의심스러운 앱 조사(2단계와 동일)
 

활동 로그 사용(3단계와 동일)
 

참조 https://searchmicroservices.techtarget.com/definition/OAuth https://docs.microsoft.com/cloud-app-security/manage-app-permissions


 
## <a name="next-steps"></a>다음 단계
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md) 

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/) 
 
