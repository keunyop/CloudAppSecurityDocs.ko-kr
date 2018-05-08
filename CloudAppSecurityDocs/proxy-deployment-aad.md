---
title: Azure AD 앱용 Microsoft Cloud App Security 조건부 액세스 앱 제어 배포| Microsoft Docs
description: 이 항목에서는 Azure AD 앱용 Microsoft Cloud App Security 조건부 액세스 앱 제어 역방향 프록시 기능을 배포하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/25/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5397fd49d1eaa2365c7909155ded55eef965e0de
ms.sourcegitcommit: c5dbeb75e409518feaa26200e9a02c59accc8dcc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
*적용 대상: Microsoft Cloud App Security*

# <a name="deploy-conditional-access-app-control-for-azure-ad-apps"></a>Azure AD 앱용 조건부 액세스 앱 제어 배포

> [!NOTE]
> 이것은 미리 보기 기능입니다.

다음 단계에 따라 Microsoft Cloud App Security 조건부 액세스 앱 제어에서 Azure AD 앱을 제어하도록 구성합니다.

> [!NOTE]
> Azure AD 앱용 조건부 액세스 앱 제어를 배포하려면 유효한 [Azure AD Premium P2 라이선스](https://docs.microsoft.com/azure/active-directory/license-users-groups)가 필요합니다.

## <a name="step-1-add-azure-ad-apps-in-cloud-app-security"></a>1단계: Cloud App Security에 Azure AD 앱 추가  

1. Azure AD 조건부 액세스 테스트 정책을 만듭니다.

   1. Azure Active Directory에서 **보안** 아래에 있는 **조건부 액세스**를 클릭합니다.

      ![Azure AD 조건부 액세스](./media/aad-conditional-access.png)

   2. **새 정책**을 클릭하고 **세션**에서 **Use Conditional Access App Control enforced restrictions**(조건부 액세스 앱 제어 적용 제한 사용)를 선택하여 새로운 정책을 만듭니다.

      ![Azure AD 조건부 액세스](./media/proxy-deploy-restrictions-aad.png)

   3. 테스트 정책의 **사용자** 아래에서 초기 로그온에 사용할 수 있는 테스트 사용자 또는 사용자를 지정합니다.
    
   4. 테스트 정책의 **클라우드 앱** 아래에서 조건부 액세스 앱 제어로 제어하려는 앱을 할당합니다. 

      > [!NOTE]
      >조건부 액세스 앱 제어에서 지원하는 앱을 선택해야 합니다. 조건부 액세스 앱 제어는 Azure AD에서 SAML Single Sign-On으로 구성된 앱을 지원합니다. 예를 들어 Office 365 응용 프로그램은 SAML로 구성되지 않으므로 현재 지원되지 않습니다.


2. 정책을 만들었으면 정책에 구성된 사용자를 사용하여 정책에 구성된 각 앱에 로그인합니다. 먼저 기존 세션에서 로그아웃해야 합니다.

3. Cloud App Security 포털에서 설정 코그로 이동하고 **Conditional Access App Control**(조건부 액세스 앱 제어)을 선택합니다. 
    
     ![프록시 메뉴](./media/proxy-menu.png)

4. ‘새 Azure AD 앱이 조건부 액세스 앱 제어에 의해 검색되었습니다.’라고 알려주는 메시지가 표시됩니다. **새 앱을 확인하세요** 링크를 클릭합니다.

   ![조건부 액세스 앱 제어 보기 새 앱](./media/proxy-view-new-apps.png)

5. 열린 대화 상자에서 이전 단계에서 로그인한 모든 앱을 볼 수 있습니다. 각 앱에 대해 + 기호를 클릭한 다음 **추가**를 클릭합니다.

   ![조건부 액세스 앱 제어 새 앱](./media/proxy-new-app.png)

   > [!NOTE]
   > 앱이 Cloud App Security 앱 카탈로그에 표시되지 않으면 로그인 URL과 함께 알 수 없는 앱 아래의 대화 상자에 나타납니다. 이러한 앱에 대한 + 기호를 클릭하면 카탈로그에 해당 앱을 추가하도록 제안할 수 있습니다. 앱이 카탈로그에 있으면 단계를 다시 수행하여 해당 앱을 배포합니다. 

6. 조건부 액세스 앱 제어 앱 테이블에서 **사용 가능한 제어** 열을 살펴보고 Azure AD 조건부 액세스와 세션 제어가 모두 표시되는지 확인합니다. <br></br>앱에 대한 세션 제어가 표시되지 않으면 해당 특정 앱에서 아직 세션 제어를 사용할 수 없다는 의미이며, **세션 제어 요청** 링크가 대신 표시됩니다. 이 링크를 클릭하여 대화 상자를 열고 세션 제어에 대한 앱 온보딩을 요청합니다. 조건부 액세스 앱 제어 공개 미리 보기 기간에 온보딩 프로세스는 사용자와 함께 Microsoft Cloud App Security 팀에서 수행합니다.
  
   ![세션 제어 요청](./media/request-session-control.png)

7. 선택 사항 - 클라이언트 인증서를 사용하여 장치를 식별합니다.

   1. 설정 코그로 이동하고 **장치 식별**을 선택합니다.

   2. 루트 인증서를 업로드합니다.

      ![장치 식별](./media/device-identification.png)
 
      인증서가 업로드되면 **장치 태그**가 **유효한 클라이언트 인증서**와 같거나 같지 않은 액세스 정책 및 세션 정책을 만들 수 있습니다.
 
      > [!NOTE]
      >세션이 유효한 클라이언트 인증서 필터를 사용하는 정책과 일치하는 경우에만 사용자에게 인증서를 요청합니다. 

## <a name="step-2-test-the-deployment"></a>2단계: 배포 테스트

1. 먼저 기존 세션에서 로그아웃합니다. 그런 다음 Azure AD에 구성된 정책과 일치하는 사용자를 사용하여 성공적으로 배포된 각 응용 프로그램에 로그인합니다. 

2. Cloud App Security 포털의 **조사** 아래에서 **활동 로그**를 선택하고 각 앱에 대해 로그인 활동이 캡처되는지 확인합니다.

3. **고급**을 클릭한 다음 **원본이 Azure Active Directory 조건부 액세스와 같음**을 사용하여 필터링할 수 있습니다.

    ![Azure AD 조건부 액세스를 사용하여 필터링](./media/sso-logon.png)

4. 활동이 활동 로그에 제대로 캡처되도록 하려면 관리 장치와 관리되지 않는 장치의 모바일 및 데스크톱 앱에 로그인하는 것이 좋습니다.<br></br>
   활동이 제대로 캡처되었는지 확인하려면 활동의 Single Sign-On 로그온 활동을 클릭하여 활동 서랍을 열고 **사용자 에이전트 태그**에서 장치가 네이티브 클라이언트(모바일 또는 데스크톱 앱)인지 또는 장치가 관리 장치(준수, 도메인 가입 또는 유효한 클라이언트 인증서)인지 여부를 제대로 반영하는지 확인합니다.
 
   ![사용자 에이전트 태그 테스트](./media/domain-joined.png)


이제 조건부 액세스 앱 제어 앱을 제어할 [액세스 정책](access-policy-aad.md) 및 [세션 정책](session-policy-aad.md)을 만들 준비가 되었습니다.



## <a name="see-also"></a>참고 항목  
[Cloud App Security 조건부 액세스 앱 제어로 작업](proxy-intro-aad.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  