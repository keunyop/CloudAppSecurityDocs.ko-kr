---
title: "Microsoft Cloud App Security에 ServiceNow 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 ServiceNow 앱을 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 30ddba23a0c481cb434e9239950cce90c52efc4f


---

# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 ServiceNow 연결
이 섹션에서는 앱 커넥터 API를 사용하여 기존 ServiceNow 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>Cloud App Security에 ServiceNow를 연결하는 방법  
  
> [!NOTE]  
>  Cloud App Security는 ServiceNow 버전의 Eureka 및 Fiji를 지원합니다. ServiceNow를 Cloud App Security와 연결하려면 관리자 수준 권한이 있어야 하며 ServiceNow 인스턴스가 API 액세스를 지원해야 합니다.  
  
1.  관리자 계정을 사용하여 ServiceNow 계정에 로그온합니다.  
  
2.  Cloud App Security에 대한 새 서비스 계정을 만들고 새로 만든 계정에 관리자 역할을 연결합니다.  
  
3.  REST API 플러그 인이 켜져 있는지 확인합니다.  
  
     ![servicenow 계정](./media/servicenow-account.png "servicenow account")  
  
4.  Cloud App Security 포털에서 **조사**, **사용 권한 앱**을 차례로 클릭합니다.  
  
5.  ServiceNow 행의 **앱 커넥터 상태** 열에서 **연결**을 클릭하거나 **앱 연결** 단추, **ServiceNow**를 차례로 클릭합니다.  
  
     ![servicenow 연결](./media/connect-servicenow.png "connect servicenow")  
  
6.  ServiceNow 설정 페이지의 API 탭에서 해당 상자에 ServiceNow 사용자 이름, 암호 및 인스턴스 URL을 추가합니다.  
  
7.  **연결**을 클릭합니다.  
  
     ![servicenow 암호 업데이트](./media/servicenow-update-password.png "servicenow update password")  
  
8.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
ServiceNow를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


