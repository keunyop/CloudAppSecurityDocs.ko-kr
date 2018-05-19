---
title: Cloud App Security의 새로운 기능 | Microsoft Docs
description: 이 항목은 자주 업데이트되어 Cloud App Security 최신 릴리스의 새로운 기능을 소개합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/11/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 545d7cb0e7152918e8f9b1e37ff1d7a210605342
ms.sourcegitcommit: aebd4dd970465a7f5818329f344c24fe73f616dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2018
---
*적용 대상: Microsoft Cloud App Security*


# <a name="whats-new-with-microsoft-cloud-app-security"></a>Microsoft Cloud App Security의 새로운 기능

## <a name="cloud-app-security-release-123"></a>Cloud App Security 릴리스 123

릴리스 날짜: 2018년 5월 13일

- **변칙 검색 정책 범위 지정**:<br>
이제 변칙 검색 정책의 범위를 지정할 수 있습니다. 따라서 특정 사용자 또는 그룹만 포함하거나 특정 사용자 또는 그룹을 제외하도록 각 변칙 검색 정책을 설정할 수 있습니다. 예를 들어, 자주 여행하는 특정 사용자를 무시하도록 자주 사용되지 않는 국가에서의 활동 검색을 설정할 수 있습니다. 


## <a name="cloud-app-security-release-122"></a>Cloud App Security 릴리스 122
릴리스 날짜: 2018년 4월 29일

-   점진적 출시: 이제 **앱별 Microsoft Cloud App Security 관리자의 관리 권한을 설정**할 수 있습니다. 예를 들어, 특정 사용자를 G Suite 전용 관리자로 설정할 수 있습니다. 이렇게 하면 사용자가 G Suite와 관련된 경우에만 Microsoft Cloud App Security에서 정보를 보고 수정할 수 있습니다. 자세한 내용은 [관리자 액세스 관리](manage-admins.md)를 참조하세요.
- 점진적 출시: 이제 **OKTA 관리자 역할이 Microsoft Cloud App Security에 표시**되며 **설정** > **사용자 그룹** 아래에서 태그로 각 역할에 대해 사용 가능합니다.


## <a name="cloud-app-security-release-121"></a>Cloud App Security 릴리스 121
릴리스 날짜: 2018년 4월 22일

-   **조건부 액세스 앱 제어(이전의 Cloud App Security 프록시)** 의 공개 미리 보기는 다양한 응용 프로그램에 대한 가시성과 제어력을 높일 수 있는 기능으로 향상되었습니다. 이제 *활동 유형* 필터로 세션 정책을 만들어 다양한 앱별 활동을 모니터링하고 차단할 수 있습니다. 이 새 필터는 기존의 파일 다운로드 제어 기능을 보강하여 조직의 응용 프로그램에 대한 포괄적인 제어를 제공하며 Azure Active Directory 조건부 액세스와 함께 사용되어 위험한 사용자 세션(예: B2B 공동 작업 사용자 세션 또는 관리되지 않는 장치의 사용자 세션)에 대한 실시간 가시성 및 제어를 제공합니다. 자세한 내용은 [세션 정책](session-policy-aad.md)을 참조하세요.
-   점진적 출시: Cloud App Security의 **변칙 검색 정책**은 랜섬웨어 활동 및 종료된 사용자 활동이라는 두 가지 새로운 유형의 위협 검색을 포함하도록 개선되었습니다. Cloud App Security는 정교한 랜섬웨어 공격으로부터 보다 포괄적인 보호를 보장하기 위해 변칙 검색으로 랜섬웨어 검색 기능을 확장했습니다. 보안 연구 전문 지식을 통해 랜섬웨어 활동을 반영하는 동작 패턴을 식별하는 Cloud App Security는 전체적이고 강력한 보호를 보장합니다. 종료된 사용자 활동을 사용하면 회사 앱에서 프로비전이 해제되지만 대부분의 경우 특정 회사 리소스에 대한 액세스 권한은 계속 유지되는 종료된 사용자의 계정을 모니터링할 수 있습니다. 자세한 내용은 [즉각적인 동작 분석 및 변칙 검색 이용](anomaly-detection-policy.md)을 참조하세요.


## <a name="cloud-app-security-release-120"></a>Cloud App Security 릴리스 120
릴리스 날짜: 2018년 4월 8일

-   Office 365 및 Azure AD를 위해 현재 Office 365 및 Azure AD 응용 프로그램(내부 및 외부 모두)에서 수행되는 사용자 계정 활동으로 내부 응용 프로그램을 감지하는 기능을 도입하고 있습니다. 이를 통해 응용 프로그램에서 예기치 않게 권한이 없는 작업을 수행할 경우 이를 경고하는 정책을 만들 수 있습니다. 
-   앱 권한 목록을 csv로 내보낼 때 규정 준수 및 조사 프로세스를 지원하기 위해 게시자, 권한 수준 및 커뮤니티 사용량과 같은 추가 필드가 포함됩니다.
-   ServiceNow 연결 앱이 개선되어 내부 서비스 활동이 더 이상 "게스트"가 수행한 것으로 등록되지 않으며 또 가양성 경고를 트리거하지 않습니다. 이러한 활동은 이제 연결된 다른 모든 앱처럼 N/A로 표시됩니다.


## <a name="cloud-app-security-release-119"></a>Cloud App Security 릴리스 119
릴리스 날짜: 2018년 3월 18일

-   IP 주소 범위 페이지에는 Cloud App Security에서 검색된 기본 제공 IP 주소가 포함됩니다. 여기에는 Azure 및 Office 365와 같이 확인된 클라우드 서비스의 IP 주소뿐만 아니라 알려진 위험 IP 주소 정보로 IP 주소를 자동으로 강화하는 위협 인텔리전스 피드가 포함됩니다. 
-   Cloud App Security가 파일에서 거버넌스 작업을 실행하려 하지만 파일이 잠겨 있어 실패하며, 지금 자동으로 거버넌스 작업을 다시 시도합니다. 

## <a name="cloud-app-security-release-118"></a>Cloud App Security 릴리스 118
릴리스 날짜: 2018년 3월 4일

- 이제 고유한 사용자 지정 앱에서 Microsoft Cloud App Security의 섀도 IT 검색 및 모니터링 기능을 활용할 수 있습니다. Cloud Discovery에 사용자 지정 앱을 추가하는 새로운 기능을 사용하면 앱 사용을 모니터링하고 사용 패턴 변경에 대한 알림을 받을 수 있습니다. 자세한 내용은 [사용자 지정 앱 보호](cloud-discovery-custom-apps.md)를 참조하세요. 이 기능은 점진적으로 출시될 예정입니다.

- Cloud App Security 포털 **설정** 페이지가 다시 디자인되었습니다. 새 디자인은 모든 설정 페이지를 통합하고 검색 기능 및 향상된 디자인을 제공합니다. 

- 이제 Cloud Discovery는 Barracuda F-Series 방화벽 및 Barracuda F-Series 방화벽 웹 로그 스트리밍을 지원합니다.

- 사용자 및 IP 주소 페이지의 검색 기능을 사용하면 자동 완성을 통해 원하는 내용을 더 쉽게 찾을 수 있습니다.

- 이제 엔터티 제외 및 IP 주소 제외 설정 페이지에서 대량 작업을 수행할 수 있습니다. 이렇게 하면 여러 사용자와 그룹 또는 IP 주소를 더욱 쉽게 선택하고 조직에서 Cloud Discovery를 통해 모니터링되지 않도록 제외할 수 있습니다. 

## <a name="cloud-app-security-release-117"></a>Cloud App Security 릴리스 117
릴리스 날짜: 2018년 2월 20일

-   Cloud App Security가 Azure Information Protection과 심층 통합되어 이제 G Suite에서 파일을 보호할 수 있습니다. 공개 미리 보기 기능을 사용하면 G Suite에서 파일을 검색 및 분류할 수 있고 Azure Information Protection 레이블을 자동으로 적용하여 보호할 수 있습니다. 자세한 내용은 [Azure Information Protection 통합](azip-integration.md)을 참조하세요.

-   이제 Cloud Discovery는 [Digital Arts i-FILTER](http://www.daj.jp/en/products/if/)를 지원합니다.

-   이제 SIEM 에이전트 표에 더 쉬운 관리를 위한 자세한 정보가 포함됩니다.

## <a name="cloud-app-security-release-116"></a>Cloud App Security 릴리스 116
릴리스 날짜: 2018년 2월 4일
- Cloud App Security의 변칙 검색 정책이 불가능한 이동, 의심스러운 IP 주소로부터의 활동, 여러 번 실패한 로그인 시도 등 새로운 **시나리오 기반 검색**으로 향상되었습니다. 새 정책은 자동으로 사용 가능하며, 클라우드 환경에서 기본 제공 위협 검색 기능을 제공합니다. 또한 새 정책은 Cloud App Security 검색 엔진의 데이터를 더 많이 공개하여 조사 프로세스를 더 빨리 진행하고 지속적으로 발견되는 위협을 포함하도록 도와줍니다. 자세한 내용은 [즉각적인 동작 분석 및 변칙 검색 이용](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy)을 참조하세요.

- 점진적 출시: Cloud App Security는 이제 SaaS 앱 전체에서 사용자와 해당 계정 간의 상관 관계를 지정합니다. 따라서 사용자가 사용한 앱 또는 계정과 관계없이 해당 사용자의 모든 다양한, 상관 관계가 지정된 SaaS 앱에서 사용자의 모든 활동을 쉽게 조사할 수 있습니다.  

-   점진적 출시: Cloud App Security는 이제 같은 연결된 앱의 여러 인스턴스를 지원합니다. 예를 들어 Salesforce의 여러 인스턴스가 있는 경우(영업용 인스턴스 하나, 마케팅용 인스턴스 하나) 이러한 인스턴스를 모두 Cloud App Security에 연결하고 같은 콘솔에서 관리하여 세분화된 정책을 만들고 더 깊이 있는 조사를 수행할 수 있습니다. 

- Cloud Discovery 파서는 이제 두 가지 추가 검사점 형식 XML 및 KPC를 지원합니다.



## <a name="cloud-app-security-release-115"></a>Cloud App Security 릴리스 115
릴리스 날짜: 2018년 1월 21일

- 이 릴리스는 파일 정책에서 특정 폴더를 선택할 때 개선된 환경을 제공합니다. 이제 정책에 포함할 여러 폴더를 쉽게 보고 선택할 수 있습니다. 
- **검색된 앱** 페이지에서: 
  - 대량 태그 지정 기능을 사용하여 사용 권한 및 비사용 권한 태그 외에 사용자 지정 태그를 적용할 수 있습니다. 
  - **IP 주소 보고서를 생성**하거나 **사용자 보고서를 생성**하면 이제 내보낸 보고서에 트래픽이 사용 권한 앱에서 온 것인지 또는 비사용 권한 앱에서 온 것인지에 대한 정보가 포함됩니다. 
- 이제 포털의 **앱 연결** 페이지에서 직접 Microsoft Cloud App Security 팀으로부터 새 API 앱 커넥터를 요청할 수 있습니다. 


## <a name="cloud-app-security-release-114"></a>Cloud App Security 릴리스 114
릴리스 날짜: 2018년 1월 7일

- 114버전부터 활동 로그 및 검색된 앱 페이지에서 사용자 지정 쿼리를 만들고 저장하는 기능을 점차적으로 제공하고 있습니다. 사용자 지정 쿼리를 사용하면 심층적인 조사를 위해 다시 사용할 수 있는 필터 템플릿을 만들 수 있습니다. 또한 활동과 검색된 앱을 필터링할 수 있도록 기본 제공되는 조사 템플릿을 제공하기 위해 **제안된 쿼리**가 추가되었습니다. **제안된 쿼리**에는 가장(impersonation) 활동, 관리자 활동, 위험한 비규격 클라우드 저장소 앱, 암호화가 약한 엔터프라이즈 앱 및 보안 위험 등과 같은 위험을 식별하는 사용자 지정 필터가 포함됩니다. **제안된 쿼리**를 시작점으로 사용하여 알맞게 수정한 다음 새 쿼리로 저장할 수 있습니다. 자세한 내용은 [활동 필터 및 쿼리](activity-filters-queries.md)와 [검색된 앱 필터 및 쿼리](discovered-app-queries.md)를 참조하세요.
 
- 이제 [status.cloudappsecurity.com](https://status.cloudappsecurity.com)으로 이동하거나 **도움말**>**시스템 상태**를 클릭하면 포털에서 현재 Cloud App Security 서비스 상태를 확인할 수 있습니다. 
 


## <a name="see-also"></a>참고 항목  

여기에 나열된 릴리스 이전의 릴리스에 대한 설명은 [Microsoft Cloud App Security의 이전 릴리스](release-note-archive.md)를 참조하세요.

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  