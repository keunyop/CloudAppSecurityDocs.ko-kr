---
title: 액세스 허용 및 차단을 위한 Cloud App Security 액세스 정책 만들기 | Microsoft Docs
description: 이 항목에서는 역방향 프록시 기능을 사용하여 Azure AD를 통해 연결된 앱에 대한 액세스를 허용하고 차단하도록 Cloud App Security 조건부 액세스 앱 제어 액세스 정책을 설정하는 절차를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9095cff1-f8b0-44a7-b1df-a83e674abbc6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f25b827c7b0ff635789a4ef721b538598729d0e9
ms.sourcegitcommit: 49a06f2169af74304eef0288e31783c06ccd3b74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2018
ms.locfileid: "36746918"
---
*적용 대상: Microsoft Cloud App Security*

# <a name="access-policies"></a>액세스 정책 



>[!div class="step-by-step"]
[« 이전: 세션 정책을 만드는 방법](session-policy-aad.md)<br>
[다음: 인기 있는 사용 사례 탐색 »](use-case-proxy-block-session-aad.md)


Microsoft Cloud App Security 액세스 정책을 통해 사용자, 위치, 장치 및 앱을 기반으로 클라우드 앱에 대한 액세스를 실시간으로 모니터링하고 제어할 수 있습니다. 클라이언트 인증서를 관리되는 장치로 롤아웃하거나 타사 MDM 인증서와 같은 기존 인증서를 활용하여 도메인에 가입하지 않은 장치 및 Windows Intune으로 관리되지 않는 장치를 비롯한 모든 장치에 대한 액세스 정책을 만들 수 있습니다. 예를 들어 관리되는 장치에 클라이언트 인증서를 배포한 다음 인증서 없이 장치에서 액세스할 수 없도록 차단할 수 있습니다. 

> [!NOTE]
> [세션 정책](session-policy-aad.md)을 통해 액세스를 완전히 허용하거나 차단하는 대신 세션을 모니터링하면서 액세스를 허용하거나 특정 세션 활동을 제한할 수 있습니다. 

## <a name="prerequisites-to-using-access-policies"></a>액세스 정책 사용을 위한 필수 구성 요소

- Azure AD Premium P2 라이선스
- 관련 앱은 [조건부 액세스 앱 제어를 사용하여 배포됩니다](proxy-deployment-aad.md).
- [Azure AD 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)이 아래에 설명된 대로 사용자를 Microsoft Cloud App Security로 리디렉션하는 위치에 있어야 합니다.

> [!NOTE]
> - 액세스 정책은 Azure AD 이외의 ID 공급자로 구성된 앱도 지원합니다. 자세한 내용은 mcaspreview@microsoft.com으로 이메일을 보내주세요.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Azure AD 조건부 액세스 정책 만들기

Azure Active Directory 조건부 액세스 정책과 Cloud App Security 세션 정책이 동시에 작동하여 각 사용자 세션을 검사하고 각 앱에 대한 정책을 결정합니다. Azure AD에서 조건부 액세스 정책을 설정하려면 다음 절차를 수행합니다.

1. 조건부 액세스 앱 제어를 통해 제어하려는 사용자 또는 사용자 그룹 및 SAML 앱에 대한 할당을 사용하여 [Azure AD 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)을 구성합니다. 

   > [!NOTE]
   > [조건부 액세스 앱 제어를 사용하여 배포](proxy-deployment-aad.md)된 앱만 이 정책에 따라 영향을 받습니다.

2. **세션** 블레이드에서 **Use Conditional Access App Control enforced restrictions**(조건부 액세스 앱 제어 적용 제한 사용)를 선택하여 사용자를 Microsoft Cloud App Security로 라우팅합니다.
 
## <a name="create-a-cloud-app-security-access-policy"></a>Cloud App Security 액세스 정책 만들기 

새 액세스 정책을 만들려면 다음 절차를 따르세요.

1. 포털에서 **제어**, **정책**을 차례로 선택합니다.
2. **정책** 페이지에서 **정책 만들기**를 클릭하고 **액세스 정책**을 선택합니다.  

3. **액세스 정책** 창에서 정책의 이름(예: *관리되지 않는 장치의 액세스 차단*)을 할당합니다.

4. **다음 항목 모두와 일치하는 활동** 섹션의 **활동 원본** 아래에서 정책에 적용할 추가 활동 필터를 선택합니다. 여기에는 다음 옵션이 포함될 수 있습니다. 
     
   - **장치 태그**: 관리되지 않는 장치를 식별하려면 이 필터를 사용합니다.

   - **위치**: 알 수 없는(이에 따라 위험한) 위치를 식별하려면 이 필터를 사용합니다. 

   - **IP 주소**: IP 주소별로 필터링하거나 이전에 할당된 IP 주소 태그를 사용하려면 이 필터를 사용합니다. 

   - **사용자 에이전트 태그**: 추론 방식으로 모바일 및 데스크톱 앱을 식별하려면 이 필터를 사용합니다. 이 필터는 **네이티브 클라이언트**와 같거나 같지 않도록 설정할 수 있으며, 각 클라우드 앱의 모바일 및 데스크톱 앱에 대해 테스트해야 합니다.
  
5. **작업** 아래에서 다음 중 하나를 선택합니다. 

    - **허용**: 설정한 정책 필터에 따라 액세스를 명시적으로 허용하려면 이 작업을 설정합니다.

    - **차단**: 설정한 정책 필터에 따라 액세스를 명시적으로 차단하려면 이 작업을 설정합니다. 

6. **정책 심각도와 일치하는 각 이벤트에 대한 경고를 만들고**, 경고 제한을 설정하고, 경고를 전자 메일, 문자 메시지 또는 둘 다로 사용할지 여부를 선택할 수 있습니다.



>[!div class="step-by-step"]
[« 이전: 세션 정책을 만드는 방법](session-policy-aad.md)<br>
[다음: 인기 있는 사용 사례 탐색 »](use-case-proxy-block-session-aad.md)

 
## <a name="see-also"></a>참고 항목  
[Azure AD 조건부 액세스 앱 제어 기능을 사용하여 관리되지 않는 장치에서 다운로드 차단](use-case-proxy-block-session-aad.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  