---
title: Cloud App Security에 ServiceNow 연결
description: 이 문서에서는 사용에 대한 표시 유형 및 제어를 위해 API 커넥터를 사용하여 Cloud App Security에 ServiceNow 앱을 연결하는 방법에 대한 정보를 제공합니다.
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
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 7c1a7789b405f9cd511f54308dacc41d7a42fcd1
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568087"
---
# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 ServiceNow 연결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 앱 커넥터 API를 사용하여 기존 ServiceNow 계정에 Microsoft Cloud App Security를 연결하기 위한 지침을 제공합니다. 이 연결은 ServiceNow 사용에 대한 표시 유형과 제어를 제공합니다.

> [!NOTE]
>  ServiceNow를 배포할 때는 Fuji 이상 릴리스에 제공되는 OAuth 앱 토큰을 사용하는 것이 좋습니다(관련 [ServiceNow documentation](https://wiki.servicenow.com/index.php?title=OAuth_Applications#gsc.tab=0)(ServiceNow 설명서)을 참조하세요. 이전 릴리스의 경우 사용자/암호를 기반으로 [레거시 연결 모델](#legacy-servicenow-connection)을 사용할 수 있습니다. 제공된 사용자 이름/암호는 API 토큰 생성에만 사용되고 초기 연결 프로세스 후에 저장되지 않습니다.
> 
> [!NOTE]
>  Cloud App Security는 Jakarta, Kingston, Eureka, Fiji, Geneva, Helsinki 및 Istanbul의 ServiceNow 버전을 지원합니다. ServiceNow를 Cloud App Security와 연결하려면 **관리자** 역할이 있어야 하며 ServiceNow 인스턴스가 API 액세스를 지원해야 합니다.  자세한 내용은 [ServiceNow Product Documentation](https://wiki.servicenow.com/index.php?title=Base_System_Roles#gsc.tab=0)(ServiceNow 제품 설명서)을 참조하세요.
  
## <a name="how-to-connect-servicenow-to-cloud-app-security-using-oauth"></a>OAuth를 사용하여 Cloud App Security에 ServiceNow를 연결하는 방법
  
  
1. 관리자 계정을 사용하여 ServiceNow 계정에 로그인합니다.  
 
   > [!NOTE]
   >  제공된 사용자 이름/암호는 API 토큰 생성에만 사용되고 초기 연결 프로세스 후에 저장되지 않습니다.

2. **Filter navigator**(필터 탐색기) 검색 창에 **OAuth**를 입력하고 **Application Registry**(애플리케이션 레지스트리)를 선택합니다.

3. **Application Registries**(애플리케이션 레지스트리) 메뉴 모음에서 **New**(새로 만들기)를 클릭하여 새 OAuth 프로필을 만듭니다.

   ![ServiceNow 새 OAuth 프로필](./media/servicenow-app-registry.png)

4. **What kind of OAuth application?**(OAuth 애플리케이션 종류)에서 **Create an OAuth API endpoint for external clients**(외부 클라이언트에 대해 OAuth API 엔드포인트 만들기)를 클릭합니다.

   ![ServiceNow OAuth 유형](./media/servicenow-oauth-app-type.png)

5. **Application Registries New record**(애플리케이션 레지스트리 새 레코드)에서 다음 필드를 입력합니다.
    
    - **Name**(이름) 필드, 새 OAuth 프로필의 이름(예: CloudAppSecurity) 
    
    - **Client ID**(클라이언트 ID)가 자동으로 생성됩니다. 이 ID를 복사합니다. Cloud App Security에 붙여넣어서 연결을 완료해야 합니다.
    
    - **Client Secret**(클라이언트 암호) 필드에 문자열을 입력합니다. 비워두는 경우 임의의 암호가 자동으로 생성됩니다. 나중을 위해 복사하고 저장합니다. 
    
    - **Access Token Lifespan**(액세스 토큰 수명)을 3,600 이상으로 늘립니다.
    
    - **제출**을 클릭합니다.

   ![ServiceNow 프로필 ID](./media/servicenow-profile-ids.png)

6. Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
7. **앱 커넥터** 페이지에서 더하기 단추, **ServiceNow**를 차례로 클릭합니다.  
  
    ![ServiceNow 연결](./media/connect-servicenow.png "ServiceNow 연결")  
  
8. 팝업에서 해당 상자에 ServiceNow 사용자 ID, 암호, 인스턴스 URL, 클라이언트 ID 및 클라이언트 암호를 추가합니다. ServiceNow 사용자 ID를 찾으려면 ServiceNow 포털에서 **사용자**로 이동한 다음, 표에서 이름을 찾습니다.

   ![ServiceNow 사용자 ID](./media/servicenow-userid.png)
  
9. **연결**을 클릭합니다.  
  
    ![CAS에 ServiceNow 연결](./media/servicenow-portal-connect.png "포털에서 ServiceNow 연결")  
  
10. **Test now**(지금 테스트)를 클릭하여 연결에 성공했는지 확인합니다.  
  
    테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
ServiceNow를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.
  
## <a name="legacy-servicenow-connection"></a>레거시 ServiceNow 연결

ServiceNow를 Cloud App Security와 연결하려면 관리자 수준 권한이 있어야 하며 ServiceNow 인스턴스가 API 액세스를 지원해야 합니다.   

1. 관리자 계정을 사용하여 ServiceNow 계정에 로그인합니다.   

2. Cloud App Security에 대한 새 서비스 계정을 만들고 새로 만든 계정에 관리자 역할을 연결합니다.   

3. REST API 플러그 인이 켜져 있는지 확인합니다.   

   ![ServiceNow 계정](./media/servicenow-account.png "ServiceNow 계정")   

4. Cloud App Security 포털에서 **조사**, **사용 권한 앱**을 차례로 클릭합니다.   

5. ServiceNow 행의 **앱 커넥터 상태** 열에서 **연결**을 클릭하거나 **앱 연결** 단추, **ServiceNow**를 차례로 클릭합니다.   

   ![ServiceNow 연결](./media/connect-servicenow.png "ServiceNow 연결")   

6. ServiceNow 설정 페이지의 API 탭에서 해당 상자에 ServiceNow 사용자 ID, 암호 및 인스턴스 URL을 추가합니다.   

7. **연결**을 클릭합니다.   

   ![ServiceNow 암호 업데이트](./media/servicenow-update-password.png "ServiceNow 암호 업데이트")   

8. **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.   
  
   테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.    
   ServiceNow를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다. 


## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
