---
title: 표시 유형 및 사용 제어를 위해 Cloud App Security에 Okta 연결 | Microsoft 문서
description: 이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Okta를 연결하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9c3673b9-99bd-400c-9da1-5bf809ea5892
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8f789798297b01ee324e3e3c824461f14eb3e9c
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2018
---
*적용 대상: Microsoft Cloud App Security*



# <a name="connect-okta-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Okta 연결
이 섹션에서는 커넥터 API를 사용하여 기존 Okta 계정에 Microsoft Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-okta-to-cloud-app-security"></a>Cloud App Security에 Okta를 연결하는 방법  
  
1.  Okta에서 Cloud App Security에 대한 관리자 서비스 계정을 만드는 것이 좋습니다.  
  
     슈퍼 관리자 권한을 가진 계정을 사용해야 합니다.  
  
     Okta 계정이 검증되었는지 확인합니다.  
  
2.  Okta 콘솔에서 **관리자**를 클릭합니다.  
  
    -   **보안**, **API**를 차례로 클릭합니다.  
  
         ![okta api](./media/okta-api.png "okta api")  
  
    -   **토큰 만들기**를 클릭합니다.  
  
         ![okta createtoken](./media/okta-createtoken.jpg "okta createtoken")  
  
    -   **토큰 만들기** 팝업에서 Cloud App Security 토큰의 이름을 지정하고 **토큰 만들기**를 클릭합니다.  
  
         ![okta 토큰 팝업](./media/okta-token-popup.png "okta 토큰 팝업")  
  
    -   **토큰이 성공적으로 생성됨** 팝업에서 **토큰 값**을 복사합니다.  
  
         ![okta 토큰 값](./media/okta-token-value.png "okta 토큰 값")  
  
3.  Cloud App Security 콘솔에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
4.  **앱 커넥터 페이지** 페이지에서 더하기 단추, **Okta**를 차례로 클릭합니다.  
  
     ![okta 연결](./media/connect-okta.png "okta 연결")  
  
5.  팝업이 열리면 **도메인** 필드에 Okta 도메인을 입력하고 **토큰** 필드에 토큰을 붙여넣습니다.  
  
6.  **연결**을 클릭하여 Cloud App Security에서 Okta에 대한 토큰을 만듭니다.  
  
7.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
Okta를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  