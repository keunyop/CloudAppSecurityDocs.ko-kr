---
title: "Microsoft Cloud App Security에 Okta 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Okta를 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a413236b04726dddc69068e39967f6ad17218719
ms.openlocfilehash: c11e133f78c3973006c3e70dd1ccd719f7b639aa


---

# <a name="connect-okta-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Okta 연결
이 섹션에서는 커넥터 API를 사용하여 기존 Okta 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-okta-to-cloud-app-security"></a>Cloud App Security에 Okta를 연결하는 방법  
  
1.  Okta에서 Cloud App Security에 대한 관리자 서비스 계정을 만드는 것이 좋습니다.  
  
     슈퍼 관리자 권한을 가진 계정을 사용해야 합니다.  
  
     Okta 계정이 검증되었는지 확인합니다.  
  
2.  Okta 콘솔에서 **관리자**를 클릭합니다.  
  
    -   **보안**, **API**를 차례로 클릭합니다.  
  
         ![okta api](./media/okta-api.png "okta api")  
  
    -   **토큰 만들기**를 클릭합니다.  
  
         ![okta createtoken](./media/okta-createtoken.jpg "okta createtoken")  
  
    -   **토큰 만들기** 팝업에서 Cloud App Security 토큰의 이름을 지정하고 **큰 만들기**를 클릭합니다.  
  
         ![okta 토큰 팝업](./media/okta-token-popup.png "okta token popup")  
  
    -   **토큰이 성공적으로 생성됨 팝업**에서 **토큰 값**을 복사합니다.  
  
         ![okta 토큰 값](./media/okta-token-value.png "okta token value")  
  
3.  Cloud App Security 콘솔에서 **조사**, **사용 권한 앱**을 차례로 클릭합니다.  
  
4.  Okta 행의 **앱 커넥터 상태** 열에서 **연결**을 클릭하거나 **앱 연결** 단추, **Okta**를 차례로 클릭합니다.  
  
     ![okta 연결](./media/connect-okta.png "connect okta")  
  
5.  API 페이지의 **도메인** 필드에 Okta 도메인을 입력하고 **토큰** 필드에 토큰을 붙여넣습니다.  
  
6.  **연결**을 클릭하여 Cloud App Security에서 Okta에 대한 토큰을 만듭니다.  
  
7.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
Okta를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


