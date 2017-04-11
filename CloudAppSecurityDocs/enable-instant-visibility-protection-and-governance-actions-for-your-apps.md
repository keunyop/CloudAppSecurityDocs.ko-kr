---
title: "앱 연결 | Microsoft 문서"
description: "이 항목에서는 조직의 클라우드에서 앱에 대해 API 커넥터를 사용하여 앱에 연결하는 프로세스에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/9/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3b15ba46-ac9c-4b4f-aefc-137edc903bc1
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a6133e3cf0521515088dfd9d301aed2df2c4b430
ms.openlocfilehash: 199a3c9909093551e3eca5e524f6bf04ce03aa4e


---

# <a name="connect-apps"></a>앱 연결 
앱 커넥터는 앱 공급자의 API를 활용하여 연결하는 앱에 대한 Cloud App Security의 제어와 표시 유형을 강화할 수 있습니다.  
  
Cloud App Security는 클라우드 공급자가 제공하는 API를 활용하며, 각 서비스에는 자체 프레임워크 및 API 제한 사항이 있습니다. Cloud App Security는 서비스와 함께 작동하여 API 사용을 최적화하고 최적의 성능을 보장합니다. 서비스에서 API에 적용하는 다양한 제한 사항(예: 제한, API 제한, 동적 시간 이동 API 창 등)을 고려하여 Cloud App Security 엔진은 허용된 용량을 활용합니다. 테넌트에 있는 모든 파일 검색 등의 일부 작업에는 대량 API가 필요하므로 보다 오랜 기간 동안에 분산됩니다. 일부 정책은 몇 시간 또는 며칠 동안 실행될 것으로 예상합니다.  
  
## <a name="how-it-works"></a>작동 방식  
Cloud App Security는 사용자 환경의 모든 개체에 대한 모든 권한을 허용하는 시스템 관리자 권한으로 배포됩니다.  
  
앱 커넥터 흐름은 다음과 같습니다.
1. Cloud App Security에서 인증 권한을 검색하고 저장합니다.
2.  Cloud App Security에서 사용자 목록을 요청합니다. 이 작업을 처음 수행하는 경우 검색이 완료될 때까지 다소 시간이 걸릴 수 있습니다. 사용자 검색이 끝나면 Cloud App Security에서 계속해서 활동 및 파일을 검색합니다. 검색이 시작되면 바로 일부 활동을 Cloud App Security에서 사용할 수 있습니다. 
4. 사용자 요청 완료 후 Cloud App Security에서 사용자, 그룹, 활동 및 파일을 주기적으로 검색합니다. 첫 번째 전체 검색 후 모든 활동을 사용할 수 있습니다. 
 
이 작업에는 다소 시간이 걸릴 수 있으며, 테넌트 크기, 사용자 수 및 검색해야 하는 파일의 크기와 수에 따라 시간이 달라집니다. 
 
연결하는 앱(아래 표 참조)에 따라 API 연결은 다음을 사용하도록 설정합니다.  
  
-   **계정 정보:**  
  
     사용자, 계정, 프로필 정보, 상태(일시 중단됨, 활성, 사용 안 함) 그룹 및 권한에 대한 표시 유형입니다.  
  
-   **감사 내역:**  
  
     사용자 활동, 관리자 활동, 로그온 활동에 대한 표시 유형입니다.  
  
-   **데이터 검색:**  
  
     주기적으로(12시간마다) 및 실시간 검색(변경이 검색될 때마다 트리거됨)의 두 프로세스를 사용하여 구조화되지 않은 데이터를 검색합니다.  
  
-   **앱 사용 권한:**  
  
     발급된 토큰 및 해당 사용 권한에 대한 표시 유형입니다.  
  
-   **계정 거버넌스:**  
  
     사용자 일시 중단, 암호 해지 등을 수행할 수 있습니다.  
  
-   **데이터 거버넌스:**  
  
     휴지통의 파일을 포함하여 파일을 격리하고 파일을 덮어쓸 수 있습니다.  
  
-   **앱 사용 권한 거버넌스:**  
  
     토큰을 제거할 수 있습니다.  
  
다음 표에서는 앱 커넥터에서 지원되는 기능을 클라우드 앱별로 보여 줍니다.  

||**Office 365**|**Box**|**Okta**|**Google Apps**|**Service Now**|**Salesforce**|**Dropbox**|**AWS**|  
|-|-|-|-|-|-|-|-|-|  
|**계정 나열**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**그룹**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**권한**|✔|✔|공급자가 지원하지 않음|✔|✔|✔|✔||  
|**사용자 거버넌스**|✔|✔||✔|서비스 예정|서비스 예정|서비스 예정||  
|**로그온 활동**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**사용자 작업**|✔*|✔|✔|✔ - Google Unlimited 필요|부분|Salesforce Shield에서 지원됨|✔|해당 없음|  
|**관리 활동**|✔|✔|✔|✔|부분|✔|✔|✔|  
|**정기적인 파일 검색**|✔|✔|해당 없음|✔|✔|✔|✔|서비스 예정|  
|**근 실시간 파일 검색**|✔|✔|해당 없음|✔ - Google Unlimited 필요|||서비스 예정||  
|**제어권 공유**|✔|✔|해당 없음|✔|해당 없음||✔||  
|**격리**|✔|✔|해당 없음|서비스 예정|||서비스 예정||  
|**앱 사용 권한 보기**|✔|공급자가 지원하지 않음|해당 없음|✔||✔|공급자가 지원하지 않음||  
|**앱 사용 권한 취소**|✔||해당 없음|✔||✔|해당 없음||  
  
  
## <a name="prerequisites"></a>필수 구성 요소  
일부 앱의 경우 Cloud App Security에서 로그를 수집할 수 있게 하고 Cloud App Security 콘솔에 대한 액세스를 제공하기 위해 허용 목록에 다음 IP 주소를 추가해야 할 수 있습니다.  
  
-   로그:  
  
     104.209.35.177  
  
     13.91.98.185  
  
-   콘솔:  
  
     104.42.231.28  

- Cloud App Security API 통합을 사용하여 연결하려는 각 앱에 대해 Cloud App Security의 전용 관리 서비스 계정을 만드는 것이 좋습니다.  
  
> [!NOTE]  
>  URL 및 IP 주소가 변경된 경우 업데이트를 가져오려면 [Office 365 URL 및 IP 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)에 설명된 대로 RSS를 구독합니다.  
  
앱 커넥터를 사용하려면 각 특정 앱에 대해 다음이 있는지 확인해야 합니다.  
  
|앱|라이선스 유형|사용자|  
|---------|------------------|----------|  
|상자|Enterprise|관리자로 Box에 연결하는 것이 좋습니다. 공동 관리자로 연결하면 일부 데이터만 표시됩니다. 공동 관리자로 연결하는 경우 모든 사용 권한을 선택해야 합니다.|  
|Google Apps|Google Apps Unlimited 선호<br /><br /> Google Apps Enterprise(최소)|슈퍼 관리자|  
|Office 365||전역 관리자|  
|AWS||새로 만든 사용자|  
|Dropbox|Business/Enterprise|관리자|  
|Okta|Enterprise(평가판 아님)|관리자|  
|Exchange||전역 관리자|  
|ServiceNow|Eureka 이상|관리자 +RestAPI 역할|  
|Salesforce||관리자|  
  

**ExpressRoute**  
  
Cloud App Security는 Azure에 배포되고 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)와 완전히 통합됩니다. 검색 로그 업로드를 포함하여 Cloud App Security에 전송된 Cloud App Security 앱 및 트래픽과의 모든 상호 작용은 대기 시간, 성능 및 보안 향상을 위해 ExpressRoute **공용 피어링**을 통해 라우팅됩니다. 고객 측에서 필요한 구성 단계는 없습니다.  
공용 피어링에 대한 자세한 내용은 [ExpressRoute 회로 및 라우팅 도메인](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
   


<!--HONumber=Jan17_HO2-->


