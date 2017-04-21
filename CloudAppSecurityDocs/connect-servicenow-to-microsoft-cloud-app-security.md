---
title: "표시 유형 및 사용 제어를 위해 Cloud App Security에 ServiceNow 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 ServiceNow 앱을 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1f4fd428f762bcbe1fb2a26bf44268cf985fbd4f
ms.sourcegitcommit: c79c405a1277c5fcebbc245fa12ff8feb53248d5
translationtype: HT
---
# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 ServiceNow 연결
이 섹션에서는 앱 커넥터 API를 사용하여 기존 ServiceNow 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>Cloud App Security에 ServiceNow를 연결하는 방법  
  
> [!NOTE]  
>  Cloud App Security는 Eureka, Fiji, Geneva, Helsinki 및 Istanbul의 ServiceNow 버전을 지원합니다. ServiceNow를 Cloud App Security와 연결하려면 **관리자** 역할이 있어야 하며 ServiceNow 인스턴스가 API 액세스를 지원해야 합니다.  자세한 내용은 [ServiceNow Product Documentation](http://wiki.servicenow.com/index.php?title=Base_System_Roles#gsc.tab=0)(ServiceNow 제품 설명서)을 참조하세요.
  
1.  관리자 계정을 사용하여 ServiceNow 계정에 로그온합니다.  
  
2.  **Filter navigator**(필터 탐색기) 검색 창에 **OAuth**를 입력하고 **Application Registry**(응용 프로그램 레지스트리)를 선택합니다.

3. **Application Registries**(응용 프로그램 레지스트리) 메뉴 모음에서 **New**(새로 만들기)를 클릭하여 새 OAuth 프로필을 만듭니다.

   ![ServiceNow 새 OAuth 프로필](./media/servicenow-app-registry.png)

4. **What kind of OAuth application?**(OAuth 응용 프로그램 종류)에서 **Create an OAuth API endpoint for external clients**(외부 클라이언트에 대해 OAuth API 끝점 만들기)를 클릭합니다.

   ![ServiceNow OAuth 유형](./media/servicenow-oauth-app-type.png)

5. **Application Registries New record**(응용 프로그램 레지스트리 새 레코드)에 다음을 입력합니다.
    
    - **Name**(이름) 필드, 새 OAuth 프로필의 이름(예: CloudAppSecurity) 
    
    - **Client ID**(클라이언트 ID)가 자동으로 생성됩니다. 이 ID를 복사합니다. Cloud App Security에 붙여넣어서 연결을 완료해야 합니다.
    
    - **Client Secret**(클라이언트 암호) 필드에 문자열을 입력합니다. 비워두는 경우 임의의 암호가 자동으로 생성됩니다. 나중을 위해 복사하고 저장합니다. 
    
    - **Access Token Lifespan**(액세스 토큰 수명)을 3,600 이상으로 늘립니다.
    
    - **제출**을 클릭합니다.

   ![ServiceNow 프로필 ID](./media/servicenow-profile-ids.png)

6.  Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
7.  **앱 커넥터** 페이지에서 더하기 단추, **ServiceNow**를 차례로 클릭합니다.  
  
     ![servicenow 연결](./media/connect-servicenow.png "servicenow 연결")  
  
8.  팝업에서 해당 상자에 ServiceNow 사용자 이름, 암호, 인스턴스 URL, 클라이언트 ID 및 클라이언트 암호를 추가합니다.  
  
9.  **연결**을 클릭합니다.  
  
     ![servicenow CAS에 연결](./media/servicenow-portal-connect.png "포털에서 servicenow 연결")  
  
10.  **Test now**(지금 테스트)를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
ServiceNow를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
