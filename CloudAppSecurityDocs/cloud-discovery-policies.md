---
title: "Cloud Discovery 정책 | Microsoft 문서"
description: "이 항목에서는 Cloud Discovery 정책 작업에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 45446111-ed1a-4699-9df5-840cc6664a6b
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: a43f96ec1d0f6047570677f07281b3e5ad42a40e


---

# <a name="cloud-discovery-policies"></a>클라우드 검색 정책
    
## <a name="creating-an-app-discovery-policy"></a>앱 검색 정책 만들기  
검색 정책을 통해 조직 내에서 새로운 앱이 검색되면 알려주는 경고를 설정할 수 있습니다.  
  
1.  콘솔에서 **제어**, **정책**을 차례로 클릭합니다.  
  
2.  **정책 만들기**를 클릭하고 **앱 검색** 정책을 선택합니다.  
  
     ![앱 검색 정책 메뉴](./media/app-discovery-policy-menu.png "app discovery policy menu")  
  
3.  정책에 이름과 설명을 지정합니다. 필요한 경우 템플릿을 기반으로 할 수 있습니다. 정책 템플릿에 대한 자세한 내용은 [정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)를 참조하세요.  
  
4.  이 정책을 트리거할 검색된 앱을 설정하려면 **필터 추가**를 클릭합니다.  
  
     필터는 필터 팝업 페이지의 왼쪽에서 선택됩니다. **앱 이름**, **도메인**, **위험 요소**, **위험 점수** 및 **범주**를 기준으로 필터링할 수 있습니다. 페이지 오른쪽에는 현재 서비스 카탈로그에서 선택한 필터에 대한 결과가 표시됩니다. 필터를 선택한 후 저장하고 필터 상자에 적절한 태그가 표시되는지 확인합니다.  
  
5.  **적용 대상**에서 **사용자**, **IP 주소** 또는 둘 다에 적용할지 여부를 선택합니다.  
  
6.  앱이 정책과 일치하기 위해 충족해야 하는 **일일 사용량 임계값**을 설정합니다.  
  
7.  **일일 경고 제한**을 설정하고 경고를 메일, 문자 메시지 또는 둘 다로 전송할지를 선택하고 필요에 따라 세부 정보를 제공합니다. 경고 설정 저장을 클릭하여 기본적으로 이후 정책에서 전화 번호, 메일 주소를 비롯한 이러한 경고 설정을 기본값으로 저장할 수 있도록 설정할 수 있습니다.  
  
8.  **만들기**를 클릭합니다.  
  
예를 들어 클라우드 환경에 있는 위험한 호스팅 앱을 검색하려는 경우 정책을 다음과 같이 설정합니다.  
  
**호스팅 서비스** 범주에 있고 위험함을 나타내는 낮은 점수를 가진 서비스를 검색하도록 정책 필터를 설정합니다.   
정책의 **심각도**를 **중간**으로 설정합니다.   
환경에서 100명이 넘는 사용자가 앱을 사용하며 서비스에서 특정 양의 데이터를 다운로드한 경우에만 검색된 특정 앱에 대해 경고를 트리거할 임계값을 맨 아래에서 설정합니다.   
또한 수신하려는 일일 경고 제한을 설정할 수 있습니다.  
  
![앱 검색 정책 예제](./media/app-discovery-policy-example.png "app discovery policy example")  
  
## <a name="cloud-discovery-anomaly-detection"></a>클라우드 검색 변칙 검색  
Cloud App Security는 Cloud Discovery의 모든 로그에서 변칙을 검색합니다. 예를 들어 이전에 Dropbox를 사용한 적이 없는 사용자가 갑자가 Dropbox에 600GB를 업로드하거나 특정 앱에서 평소보다 많은 트랜잭션이 있는 경우입니다. 기본적으로는 변칙 검색 정책은 사용하도록 설정되어 있으므로 작동하기 위해 새 정책을 구성할 필요가 없지만 기본 정책에서 경고를 받으려는 변칙 유형을 미세 조정할 수 있습니다.  
  
1.  콘솔에서 **제어**, **정책**을 차례로 클릭합니다.  
  
2.  **정책 만들기**를 클릭하고 **클라우드 검색 변칙 검색 정책**을 선택합니다.  
  
     ![cloud discovery 변칙 검색 정책 메뉴](./media/cloud-discovery-anomaly-detection-policy-menu.png "cloud discovery anomaly detection policy menu")  
  
3.  정책에 이름과 설명을 지정합니다. 필요한 경우 템플릿을 기반으로 할 수 있습니다. 정책 템플릿에 대한 자세한 내용은 [정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)를 참조하세요.  
  
4.  이 정책을 트리거할 검색된 앱을 설정하려면 **필터 추가**를 클릭합니다.  
  
     필터는 필터 팝업 페이지의 왼쪽에서 선택됩니다. 서비스 이름, 도메인, 위험 요소, 위험 점수 및 범주를 기준으로 필터링할 수 있습니다. 페이지 오른쪽에는 현재 서비스 카탈로그에서 선택한 필터에 대한 결과가 표시됩니다. 필터를 선택한 후 저장하고 필터 상자에 적절한 태그가 표시되는지 확인합니다.  
  
5.  **적용 대상**에서 **모든 데이터 뷰** 또는 **특정 데이터 뷰**에 적용할지 여부 및 **사용자**, **IP 주소** 또는 둘 다에 적용할지 여부를 선택합니다.  
  
6.  **날짜 이후에 발생한 의심스러운 활동에 한해 경고 생성**에서 경고를 트리거할 비정상적인 활동이 발생한 날짜를 선택합니다.  
  
7.  **경고**에서 변칙 검색 민감도를 낮음에서 높음으로 설정하여 수신할 경고의 빈도를 구성할 수 있습니다.  
**일일 경고 제한**을 설정하고 경고를 메일, 문자 메시지 또는 둘 다로 전송할지를 선택하고 필요에 따라 세부 정보를 제공합니다. 경고 설정 저장을 클릭하여 기본적으로 이후 정책에서 전화 번호, 메일 주소를 비롯한 이러한 경고 설정을 기본값으로 저장할 수 있도록 설정할 수 있습니다. **조직 기본값 사용**을 클릭하여 이러한 설정을 조직의 기본값에 따라 설정할 수 있습니다.  
  
9. **만들기**를 클릭합니다.  
  
![새 검색 변칙 정책](./media/new-discovery-anomaly-policy.png "new discovery anomaly policy")  
  
## <a name="see-also"></a>참고 항목  
[사용자 활동 정책](user-activity-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->

