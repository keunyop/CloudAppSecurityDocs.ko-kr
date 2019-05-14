---
title: Azure AD 앱용 Cloud App Security 조건부 액세스 앱 제어 배포
description: 이 문서에서는 Azure AD 앱용 Microsoft Cloud App Security 조건부 액세스 앱 제어 역방향 프록시 기능을 배포하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 2/2/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 14e5f822c5075f1d59dc7ecef350b46e3c8c0f0c
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568673"
---
# <a name="deploy-conditional-access-app-control-for-azure-ad-apps"></a>Azure AD 앱용 조건부 액세스 앱 제어 배포

*적용 대상: Microsoft Cloud App Security*

>[!div class="step-by-step"]
[« 이전: 조건부 액세스 앱 제어 소개](proxy-intro-aad.md)<br>
[다음: 세션 정책을 만드는 방법 »](session-policy-aad.md)


다음 단계에 따라 Microsoft Cloud App Security 조건부 액세스 앱 제어에서 Azure AD 앱을 제어하도록 구성합니다.

**1단계: [Azure AD 포털로 이동하여 앱에 대한 조건부 액세스 정책을 만들고 세션을 Cloud App Security](#add-azure-ad)로 라우팅합니다.**

**2단계: [앱에서 정책 범위에 속한 사용자로 로그인합니다](#sign-in-scoped).**

**3단계: Azure AD에서 기본 제공 Cloud App Security 정책을 선택하지 않았거나 기능이 없는 앱에 정책을 적용하려는 경우, [Cloud App Security 포털로 이동](#portal)**

[**4단계: 배포 테스트**](#test)

> [!NOTE]
> Azure AD 앱용 조건부 액세스 앱 제어를 배포하려면 유효한 [Azure AD Premium P1 라이선스](https://docs.microsoft.com/azure/active-directory/license-users-groups)와 Cloud App Security 라이선스가 필요합니다.

## 1단계: Azure AD 조건부 액세스 테스트 정책 만들기<a name="add-azure-ad"></a>  

1. Azure Active Directory에서 **보안** 아래에 있는 **조건부 액세스**를 클릭합니다.

2. **새 정책**을 클릭하고 새 정책을 만듭니다.
   
3. 테스트 정책의 **사용자** 아래에서 초기 로그온 및 인증에 사용할 수 있는 테스트 사용자 또는 사용자를 할당합니다.
    
4. 테스트 정책의 **클라우드 앱** 아래에서 조건부 액세스 앱 제어로 제어하려는 앱을 할당합니다. 
    
5. **세션**에서 기본 제공 정책인 **모니터 전용**과 **다운로드 차단** 중 하나를 적용하도록 설정합니다. 또는 **사용자 지정 정책 사용**을 선택하여 Cloud App Security 포털에서 고급 정책을 설정합니다. 

6. 해당되는 **조건 할당** 또는 **제어권 승인**(선택 사항)을 추가합니다.

   ![Azure AD 조건부 액세스](./media/azure-ad-caac-policy.png)

  
      > [!NOTE]
      >조건부 액세스 앱 제어는 이러한 추천 앱을 포함하여 Azure AD에서 Single Sign-On으로 구성된 SAML 또는 Open ID 연결 앱을 지원합니다. 비추천 앱은 세션 제어와 함께 온보드로 요청하여 Cloud App Security 포털에서 액세스 제어로 구성할 수 있습니다. 

## 2단계: 앱에서 정책 범위에 속한 사용자로 로그인 <a name="sign-in-scoped"></a>

정책을 만든 후에는 해당 정책에 구성된 각 앱에 로그인합니다. 정책에 구성된 사용자를 사용하여 로그인했는지 확인합니다. 먼저 기존 세션에서 로그아웃해야 합니다.

Cloud App Security는 로그인하는 각 새 앱에 대한 정책 세부 정보를 해당 서버에 동기화합니다.  여기에는 최대 1분이 소요될 수 있습니다.

## 3단계: Cloud App Security 포털에서 고급 컨트롤 및 비추천 앱 구성 <a name="portal"></a>

위의 지침을 따르면 Azure AD에서 직접 추천 앱에 대한 기본 제공 Cloud App Security 정책을 만들 수 있습니다.

고급 정책을 구성하려면 Cloud App Security 포털에서 [액세스 정책](access-policy-aad.md)이나 [세션 정책](session-policy-aad.md)을 만듭니다.

비추천 애플리케이션에 대한 지원을 요청하려면:

1.  Cloud App Security 포털에서 설정 코그로 이동하고 **Conditional Access App Control**(조건부 액세스 앱 제어)을 선택합니다. ‘새 Azure AD 앱이 조건부 액세스 앱 제어에 의해 검색되었습니다.’라고 알려주는 메시지가 표시됩니다. 

     ![조건부 액세스 앱 제어 메뉴](./media/caac-menu.png)

2. **새 앱 보기**를 클릭합니다.

    ![조건부 액세스 앱 제어 보기 새 앱](./media/caac-view-apps.png)
     

3. 열린 화면에서 이전 단계에서 로그인한 모든 앱을 볼 수 있습니다. 각 앱에 대해 + 기호를 클릭한 다음 **추가**를 클릭합니다.

   > [!NOTE]
   > 앱이 Cloud App Security 앱 카탈로그에 표시되지 않으면 로그인 URL과 함께 알 수 없는 앱 아래의 대화 상자에 나타납니다. 이러한 앱의 + 기호를 클릭하면 애플리케이션을 사용자 지정 앱으로 온보드할 수 있습니다.

   ![조건부 액세스 앱 제어가 검색된 Azure AD 앱](./media/caac-discovered-aad-apps.png)

4. 조건부 액세스 앱 제어 앱 테이블에서 **사용 가능한 제어** 열을 살펴보고 **Azure AD 조건부 액세스**와 **세션 제어**가 모두 표시되는지 확인합니다. 
   
   > [!NOTE]
   > 앱에 대해 세션 제어가 표시되지 않으면 특정 앱에서 세션 제어를 사용할 수 없습니다. 대신 **세션 제어 요청** 링크가 표시됩니다. 
  
     ![조건부 액세스 앱 제어 요청](./media/caac-request.png)
   

5. **세션 제어 요청**을 클릭하여 앱을 세션 제어에 온보딩하도록 요청합니다. 온보딩 프로세스는 Microsoft Cloud App Security 팀에서 수행합니다.
 

6.  클라이언트 인증서를 사용하여 디바이스를 식별합니다(선택 사항).
    1.  설정 코그로 이동하고 **디바이스 식별**을 선택합니다.
    2.  하나 이상의 루트 또는 중간 인증서를 업로드 합니다.
   
    3. 인증서가 업로드되면 **디바이스 태그** 및 **유효한 클라이언트 인증서**를 기반으로 액세스 정책 및 세션 정책을 만들 수 있습니다.

       ![조건부 액세스 앱 제어 디바이스 ID](./media/caac-device-id.png)

> [!NOTE]
> 세션이 유효한 클라이언트 인증서 필터를 사용하는 정책과 일치하는 경우에만 사용자에게 인증서를 요청합니다.


## 4단계: 배포 테스트 <a name="test"></a>

1. 먼저 기존 세션에서 로그아웃합니다. 그런 다음, 성공적으로 배포된 각 앱에 로그인합니다. Azure AD에 구성된 정책과 일치하는 사용자를 사용하여 로그인합니다. 

2. Cloud App Security 포털의 **조사** 아래에서 **활동 로그**를 선택하고 각 앱에 대해 로그인 활동이 캡처되는지 확인합니다.

3. **고급**을 클릭한 다음, **원본이 액세스 제어와 같음**을 사용하여 필터링할 수 있습니다.

    ![Azure AD 조건부 액세스를 사용하여 필터링](./media/sso-logon.png)

4. 관리되는 디바이스와 관리되지 않는 디바이스에서 모바일 및 데스크톱 앱에 로그인하는 것이 좋습니다. 이는 활동이 활동 로그에 제대로 캡처되었는지 확인하기 위한 것입니다.<br></br>
   활동이 제대로 캡처되었는지 확인하려면 활동의 Single Sign-On 로그를 클릭하여 활동 서럽을 엽니다. **사용자 에이전트 태그**에서 디바이스가 네이티브 클라이언트(모바일 또는 데스크톱 앱)인지 또는 디바이스가 관리 디바이스(준수, 도메인 가입 또는 유효한 클라이언트 인증서)인지 여부를 제대로 반영하는지 확인합니다.
 
> [!NOTE]
> 배포된 후에는 조건부 액세스 앱 제어 페이지에서 앱을 제거할 수 없습니다. 앱에서 세션 또는 액세스 정책을 설정하지 않는 한, 조건부 액세스 앱 제어는 앱의 동작을 변경하지 않습니다. 

>[!div class="step-by-step"]
[« 이전: 조건부 액세스 앱 제어 소개](proxy-intro-aad.md)<br>
[다음: 세션 정책을 만드는 방법 »](session-policy-aad.md)


## <a name="next-steps"></a>다음 단계 
[Cloud App Security 조건부 액세스 앱 제어로 작업](proxy-intro-aad.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
