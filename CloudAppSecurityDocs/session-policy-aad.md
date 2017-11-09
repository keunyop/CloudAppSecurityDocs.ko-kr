---
title: "세션 정책을 만들어서 사용자 세션에 대한 심층적인 가시성을 확보하고 다운로드를 차단 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security Proxy 세션 정책을 만들어서 사용자의 세션 활동에 대한 심층적인 가시성을 확보하고 다운로드를 차단하는 절차를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 745df28a-654c-4abf-9c90-203841169f90
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 97ebb7db49fcf5ed524a05943557d616487294f8
ms.sourcegitcommit: 3bc510959e66a29d474cbef412deac0daefa8a24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="session-policies"></a>세션 정책 

> [!NOTE]
> Microsoft Cloud App Security 프록시 기능 배포를 시작했습니다.

Cloud App Security 세션 정책을 사용하면 실시간 세션 수준 모니터링에서 클라우드 앱에 대한 세부적인 가시성을 제공하고 사용자 세션에 설정한 정책에 따라 다른 작업을 수행할 수 있습니다. 세션 제어를 통해 액세스를 완전히 허용하거나 차단하는 대신 세션을 모니터링하면서 액세스를 허용하거나 특정 세션 활동을 제한할 수 있습니다. 

예를 들어 관리되지 않는 장치 또는 특정 위치에서 오는 세션에 대해 사용자가 응용 프로그램에 액세스할 수 있도록 허용하고 중요한 파일의 다운로드도 제한하도록 결정하거나, 다운로드 시 특정 문서를 보호하도록 요구할 수 있습니다. 세션 정책을 통해 이러한 사용자 세션 제어를 설정할 수 있습니다. 

## <a name="prerequisites-to-using-session-policies"></a>세션 정책을 사용하기 위한 필수 구성 요소

- Azure AD Premium P2 라이선스
- 관련 앱은 [프록시를 사용하여 배포](proxy-deployment-aad.md)해야 합니다.
- [Azure AD 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)이 아래에 설명된 대로 사용자를 Cloud App Security 프록시로 리디렉션하는 위치에 있어야 합니다.


## <a name="create-an-azure-ad-conditional-access-policy"></a>Azure AD 조건부 액세스 정책 만들기

Azure Active Directory 조건부 액세스 정책과 Cloud App Security 세션 정책이 동시에 작동하여 각 사용자 세션을 검사하고 각 앱에 대한 정책을 결정합니다. Azure AD에서 조건부 액세스 정책을 설정하려면 다음 절차를 수행합니다.

1. Cloud App Security 프록시를 통해 제어하려는 사용자 또는 사용자 그룹 및 SAML 앱에 대한 할당을 사용하여 [Azure AD 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)을 구성합니다. 

  > [!NOTE]
  > [프록시를 사용하여 배포](proxy-deployment-aad.md)된 앱만 이 정책에 따라 영향을 받습니다.

2. **세션** 블레이드에서 **프록시 적용 제한 사용**을 선택하여 사용자를 Cloud App Security 프록시로 라우팅합니다.

 ![프록시 제한 Azure AD 조건부 액세스](./media/proxy-deploy-restrictions-aad.png)

## <a name="create-a-cloud-app-security-session-policy"></a>Cloud App Security 세션 정책 만들기 

새 세션 정책을 만들려면 다음 절차를 따르세요.

1. 포털에서 **제어**, **정책**을 차례로 선택합니다.
3. **정책** 페이지에서 **정책 만들기**를 클릭하고 **세션 정책**을 선택합니다.  

 ![세션 정책 만들기](./media/create-session-policy.png)

4. **세션 정책** 창에서 *마케팅 사용자용 Box에서 중요한 문서 다운로드 차단*과 같은 정책 이름을 지정합니다.

 ![새 세션 정책](./media/new-session-policy.png)

5. **세션 제어 유형** 필드에서 

    1. 사용자별 활동만 모니터링하려면 **모든 활동 모니터링**을 선택합니다.

    2. 사용자 활동을 모니터링하고 사용자를 위한 다운로드 차단 또는 보호와 같은 추가 작업을 수행하려면 **모든 활동 모니터링 및 파일 다운로드 제어**를 선택합니다.

    ![세션 정책 제어 유형](./media/session-policy-control-type.png)

6. **다음 항목 모두와 일치하는 활동** 섹션의 **활동 원본** 아래에서 정책에 적용할 추가 활동 필터를 선택합니다. 여기에는 다음 옵션이 포함될 수 있습니다. 

     - **장치 태그**: 관리되지 않는 장치를 식별하려면 이 필터를 사용합니다.

     - **위치**: 알 수 없는(이에 따라 위험한) 위치를 식별하려면 이 필터를 사용합니다. 

     - **IP 주소**: IP 주소별로 필터링하거나 이전에 할당된 IP 주소 태그를 사용하려면 이 필터를 사용합니다. 

     - **사용자 에이전트 태그**: 추론 방식으로 모바일 및 데스크톱 앱을 식별하려면 이 필터를 사용합니다. 이 필터는 **네이티브 클라이언트**와 같거나 같지 않도록 설정할 수 있으며, 각 클라우드 앱의 모바일 및 데스크톱 앱에 대해 테스트해야 합니다.
         
         ![네이티브 클라이언트 지원](./media/user-agent-tag.png)

       >[!NOTE]
       >세션 정책은 모바일 및 데스크톱 앱을 지원하지 않습니다. 세션 정책을 테스트하여 모바일 및 데스크톱 앱 기능을 방해하지 않는지 확인해야 합니다. 필요에 따라 모바일 및 데스크톱 앱을 세션 정책에서 제외합니다.

     ![세션 정책 활동 원본](./media/session-policy-activity-filters.png)

7. **모든 활동 모니터링 및 파일 다운로드 제어** 옵션을 선택한 경우

    1. **다음 항목 모두와 일치하는 파일**의 **활동 원본** 아래에서 정책에 적용할 추가 파일 필터를 선택합니다. 여기에는 다음 옵션이 포함될 수 있습니다.

        - **분류 레이블** - 조직에서 Azure Information Protection을 사용하고 데이터가 분류 레이블로 보호되는 경우 이 필터를 사용합니다. 그러면 여기서 적용한 분류 레이블에 따라 파일을 필터링할 수 있습니다. Cloud App Security와 Azure Information Protection의 통합에 대한 자세한 내용은 [Azure Information Protection 통합](azip-integration.md)을 참조하세요.

        - **파일 이름** - 특정 파일에 정책을 적용하려면 이 필터를 사용합니다.

        - **파일 형식** - 정책을 특정 파일 형식(예: 모든 .xls 파일에 대한 다운로드 차단)에 적용하려면 이 필터를 사용합니다.

         ![세션 정책 파일 필터](./media/session-policy-file-filters.png)

        
    2. **콘텐츠 검사** 섹션에서 DLP 엔진을 통해 문서 및 파일 콘텐츠를 검사하도록 설정할지 여부를 지정합니다.
 
     ![세션 정책 콘텐츠 검사](./media/session-policy-content-inspection.png)

    3. **작업** 아래에서 다음 중 하나를 선택합니다. 

        - **허용**: 명시적으로 설정한 정책 필터에 따라 다운로드를 허용하려면 이 작업을 설정합니다.

        - **차단**: 명시적으로 설정한 정책 필터에 따라 다운로드를 차단하려면 이 작업을 설정합니다. 자세한 내용은 [다운로드 차단 작동 방식](#block-download)을 참조하세요.

        - **보호**: 조직에서 Azure Information Protection을 사용하는 경우 Azure Information Protection에서 설정한 분류 레이블을 파일에 적용하려면 **작업**을 설정할 수 있습니다. 자세한 내용은 [다운로드 보호 작동 방식](#protect-download)을 참조하세요.

         ![세션 정책 작업](./media/session-policy-actions.png)

10. **정책 심각도와 일치하는 각 이벤트에 대한 경고를 만들고**, 경고 제한을 설정하고, 경고를 전자 메일, 문자 메시지 또는 둘 다로 사용할지 여부를 선택할 수 있습니다.

    ![세션 정책 경고](./media/session-policy-alert.png)


## <a name="how-session-monitoring-works"></a>세션 모니터링 작동 방식

세션 정책을 만들면 정책과 일치하는 각 사용자 세션이 앱이 아닌 프록시 세션 제어로 직접 리디렉션됩니다. 세션이 모니터링되고 있음을 알려주는 모니터링 알림이 사용자에게 표시됩니다.

   ![세션 모니터링 알림](./media/session-monitoring-notice.png)

사용자에게 모니터링하고 있음을 알리지 않으려면 알림 메시지를 해제할 수 있습니다.

1. 설정 코그 아래에서 **일반 설정**을 선택합니다. 

2. 그런 다음 Cloud App Security 프록시 설정 아래에서 **사용자 알림** 확인란을 선택 취소합니다.

    ![세션 모니터링 알림 사용 해제](./media/disable-session-monitoring-notice.png)

세션 내에서 사용자를 유지하기 위해 프록시는 앱 세션 내에서 관련된 모든 URL, Java 스크립트 및 쿠키를 프록시 URL로 바꿉니다. 예를 들어 앱에서 도메인이 myapp.com으로 끝나는 링크가 포함된 페이지를 반환하는 경우 프록시는 연결을 myapp.com.us.cas.ms와 같이 끝나는 도메인으로 바꿉니다. 이렇게 하면 전체 세션이 프록시에서 모니터링됩니다.

프록시는 라우팅된 모든 사용자 세션의 트래픽 로그를 기록합니다. 트래픽 로그에는 시간, IP, 사용자 에이전트, 방문한 URL 및 업로드 및 다운로드한 바이트 수가 포함됩니다. 이러한 로그가 분석되고 **Cloud App Security Proxy**라는 연속 보고서가 Cloud Discovery 대시보드의 Cloud Discovery 보고서 목록에 추가됩니다.

![프록시 보고서](./media/proxy-report.png)


이러한 로그를 내보내려면 다음을 수행합니다.

1. 설정 코그로 이동하고 **프록시**를 클릭합니다.
2. 테이블의 오른쪽에서 내보내기 단추를 클릭합니다 ![내보내기 단추](./media/export-button.png). 
3. 보고서 범위를 선택하고 **내보내기**를 클릭합니다. 이 프로세스는 다소 시간이 걸릴 수 있습니다.

내보낸 로그를 다운로드하려면 다음을 수행합니다.

1. 보고서가 준비되면 **조사**, **사용자 지정 보고서**로 차례로 이동합니다.
2. 테이블에서 **프록시 트래픽 로그** 목록에서 관련 보고서를 선택하고 다운로드 ![다운로드 단추](./media/download-button.png) 단추를 클릭합니다. 


## 다운로드 차단 작동 방식 <a name="block-download"></a>

**차단**을 Cloud App Security 프록시 세션 정책에서 수행하려는 **작업**으로 설정하면 프록시에서 사용자가 정책의 파일 필터에 따라 파일을 다운로드할 수 없도록 합니다. 다운로드 이벤트가 각 SAML 앱에 대한 프록시에서 인식되고, 사용자가 이 이벤트를 시작하면 프록시에서 실시간으로 해당 이벤트가 실행되지 않도록 개입합니다. 사용자가 다운로드를 시작한 신호가 수신되면, 프록시에서 **제한된 다운로드** 메시지를 사용자에게 보내고, 다운로드한 파일을 프록시 세션 정책에서 구성할 수 있는 사용자 지정 가능한 메시지가 포함된 텍스트 파일로 바꿉니다.  

## 다운로드 보호 작동 방식 <a name="protect-download"></a>

**보호**를 Cloud App Security 프록시 세션 정책에서 수행할 **작업**으로 설정하면 프록시에서 정책의 파일 필터에 따라 파일의 레이블 지정과 후속 보호를 적용합니다. 레이블은 Azure의 Azure Information Protection 콘솔에서 구성되며, 클라우드 앱 보안 정책에서 옵션으로 표시되도록 레이블 내에서 해당 레이블에 대해 **보호**를 선택해야 합니다. 레이블을 선택하고 Cloud App Security 정책 기준을 충족하는 파일을 다운로드하는 경우 다운로드 시 이 레이블과 해당 보호(권한 포함)가 파일에 적용됩니다. 이제 다운로드한 파일이 보호되는 동안 원본 파일은 있는 그대로 클라우드 앱에 남아 있습니다. 파일에 액세스하려는 사용자는 적용된 보호에 의해 결정된 권한 요구 사항을 충족해야 합니다.  
 
  
## <a name="see-also"></a>참고 항목  
[Azure AD 프록시 기능을 사용하여 관리되지 않는 장치에서 다운로드 차단](use-case-proxy-block-session-aad.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  