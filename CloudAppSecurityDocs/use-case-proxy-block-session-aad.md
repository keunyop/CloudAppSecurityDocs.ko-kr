---
title: Cloud App Security 프록시를 사용하여 관리되지 않는 장치로의 중요한 데이터 다운로드를 차단하는 방법 | Microsoft Docs
description: 이 항목에서는 Azure AD 프록시 기능을 사용하여 관리되지 않는 장치에서 중요한 데이터를 다운로드하지 못하도록 하여 조직을 보호하는 시나리오를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 06238ebc-2088-4372-9412-96cceaf3b145
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: eb0e0eef92181f14d83f6c4c5eaf30023b5d80da
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2018
---
*적용 대상: Microsoft Cloud App Security*


# <a name="blocking-downloads-of-sensitive-information-using-the-microsoft-cloud-app-security-proxy"></a>Microsoft Cloud App Security 프록시를 사용하여 중요한 정보 다운로드 차단


오늘날 IT 관리자는 직원의 생산성을 높이는 데 있어 진퇴양난에 놓여 있습니다. 즉 직원이 언제든지 어떤 장치에서든 작업할 수 있도록 앱에 액세스할 수 있어야 합니다. 다른 한편으로는 자산 정보와 특수 정보를 포함하는 회사 자산을 보호해야 합니다. 데이터를 보호하는 동시에 직원이 클라우드 앱에 액세스할 수 있게 하려면 어떻게 해야 할까요? **이 사용 사례에서는 관리되지 않는 장치 또는 회사 네트워크 외부 위치에서 엔터프라이즈 클라우드 앱의 중요한 데이터에 액세스할 수 있는 사용자가 다운로드할 수 없도록 차단합니다.**


## <a name="the-threat"></a>위협
조직의 계정 관리자가 주말에 집에서 개인용 랩톱의 Salesforce에서 무언가를 확인하려고 합니다. Salesforce 데이터에는 고객의 신용 카드 정보 또는 개인 정보가 포함되어 있을 수 있습니다. 가정용 PC는 관리되지 않습니다. 즉 이 PC에 Salesforce 문서를 다운로드하는 경우 맬웨어에 감염될 수 있거나, 분실되거나 도난당하는 경우 암호로 보호되지 않을 수 있으며 이를 발견한 사람은 중요한 정보에 액세스할 수 있습니다. 

## <a name="the-solution"></a>해결 방법
Azure AD 조건부 액세스와 Cloud App Security 프록시를 사용하여 클라우드 앱 사용을 모니터링하고 제어하여 조직을 보호합니다.  

## <a name="prerequisites"></a>필수 구성 요소

- 유효한 Azure AD Premium P2 라이선스
- Azure AD에서 클라우드 앱에 대한 SSO 구성  
- [앱이 Cloud App Security에 배포](proxy-deployment-aad.md)되어 있어야 합니다.

## <a name="create-a-block-download-policy-for-unmanaged-devices"></a>관리되지 않는 장치에 대한 다운로드 차단 정책 만들기  

Cloud App Security 세션 정책을 사용하면 장치 상태에 따라 세션을 자세히 제한할 수 있습니다. 해당 장치를 조건으로 사용하여 세션을 제어하려면 이를 수행하는 조건부 액세스 정책과 세션 정책을 모두 만들어야 합니다.  

### <a name="step-1-create-an-azure-ad-conditional-access-policy"></a>1단계: Azure AD 조건부 액세스 정책 만들기

1. 할당된 사용자 및 앱을 사용하여 Azure AD 조건부 액세스 정책을 만듭니다.
2. 조건부 액세스 정책의 세션 제어 아래에서 **프록시 적용 제한 사용**을 선택합니다.   

   ![Azure AD 조건부 액세스](./media/proxy-deploy-restrictions-aad.png)

이 작업이 완료되면 Cloud App Security 포털로 이동하여 세션의 파일 다운로드를 모니터링하고 제어하는 세션 정책을 만듭니다.

### <a name="step-2-create-a-session-policy"></a>2단계: 세션 정책 만들기

1. Cloud App Security 포털에서 **제어**, **정책**을 차례로 선택합니다. 

2. **정책** 페이지에서 **정책** 만들기, **세션 정책**을 차례로 클릭합니다.
 
   ![세션 정책 만들기](./media/create-session-policy.png)

3. **세션 정책 만들기** 페이지에서 정책에 대한 이름과 설명을 제공합니다. 예를 들어 **관리되지 않는 장치의 Salesforce에서 다운로드 차단**이 있습니다.

4. **정책 심각도** 및 **범주**를 할당합니다.

   ![새 세션 정책](./media/new-session-policy.png)

5. **세션 컨트롤 형식**에서 **파일 다운로드 제어(DLP 포함)** 를 선택합니다. 그러면 Salesforce 세션 내에서 사용자가 수행하는 모든 작업을 모니터링할 수 있고, 실시간으로 다운로드를 차단하거나 보호할 수 있습니다.

   ![세션 정책 제어 유형](./media/session-policy-control-type.png)

6. **다음 항목 모두와 일치하는 활동** 섹션의 **활동 원본** 아래에서 다음 필터를 선택합니다. 
    
   - **장치 태그**: **같지 않음**을 선택한 다음, 조직에서 관리 장치를 식별하는 데 사용되는 방법에 따라 **준수**, **도메인 가입** 또는 **유효한 클라이언트 인증서**를 선택합니다. 
    
   - **앱**: 제어하려는 앱을 선택합니다.  

   - **사용자**: 모니터링하려는 사용자를 선택합니다.  
    
7. 또는 회사 네트워크에 속하지 않은 위치에 대한 다운로드를 차단하려면 **다음 항목 모두와 일치하는 활동** 섹션의 **활동 원본** 아래에서 다음 필터를 설정합니다. 

   - **IP 주소** 또는 **위치**: 이러한 두 매개 변수 중 하나를 사용하여 사용자가 중요한 데이터에 액세스하려고 하는 회사 이외의 위치 또는 알 수 없는 위치를 식별할 수 있습니다.

     > [!NOTE]
     > 관리되지 않는 장치와 회사 이외의 위치로부터의 다운로드를 차단하려면 위치를 사용하여 **활동 원본**을 설정하는 세션 정책 및 **활동 원본**을 관리되지 않는 장치로 설정하는 세션 정책을 만들어야 합니다.
 
   - **앱**: 제어하려는 앱을 선택합니다.    
   
   - **사용자**: 모니터링하려는 사용자를 선택합니다.  

8. **다음 항목 모두와 일치하는 파일** 섹션의 **활동 원본** 아래에서 다음 필터를 설정합니다. 
   
   - **분류 레이블**: Azure Information Protection 분류 레이블을 사용하고 특정 Azure Information Protection Classification 레이블에 따라 파일을 필터링하려는 경우에 설정합니다.
   
   - **파일 이름** 또는 **파일 형식**을 선택하여 이 설정에 기반한 제한 사항을 적용합니다.
 
     ![세션 정책 파일 필터](./media/session-policy-file-filters.png)

9. **콘텐츠 검사**를 사용하도록 설정하여 내부 DLP에서 중요한 콘텐츠에 대해 파일을 검색할 수 있게 합니다. 

   ![세션 정책 콘텐츠 검사](./media/session-policy-content-inspection.png)

10. **작업** 아래에서 **차단**을 선택합니다. 파일을 다운로드할 수 없는 경우 사용자가 받을 차단 메시지를 사용자 지정합니다.  

    ![세션 정책 작업](./media/session-policy-actions.png)

11. 정책이 일치할 때 수신할 경고를 설정합니다. 경고를 너무 많이 받지 않도록 제한을 설정할 수 있고, 경고를 전자 메일 메시지, 문자 메시지 또는 둘 다로 가져올지를 선택할 수 있습니다.

    ![세션 정책 경고](./media/session-policy-alert.png)


12. **만들기**를 클릭합니다.  
 

## <a name="validate-your-policy"></a>정책 유효성 검사 

1. 관리되지 않는 장치 또는 회사 네트워크 외부 위치에서 차단된 파일 다운로드를 시뮬레이션하려면 앱에 로그인하여 파일 다운로드를 시도합니다. 

2. 파일이 차단되어야 하며, **차단 메시지 사용자 지정**에서 설정한 메시지가 표시되어야 합니다. 

   ![다운로드 차단 메시지](./media/block-download-message.png)

3. Cloud App Security 포털에서 **제어**, **정책**을 차례로 클릭한 다음, 만든 정책을 클릭하여 정책 보고서를 확인합니다. 세션 정책 일치 항목이 곧 표시됩니다. 
 
   ![세션 정책 보고서](./media/session-policy-report.png)

4. 정책 보고서에서 세션 제어에 대해 프록시로 리디렉션되는 로그인 및 모니터링된 세션에서 다운로드되거나 차단된 파일을 확인할 수 있습니다.




## <a name="see-also"></a>참고 항목  
[세션 정책 만들기](session-policy-aad.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  