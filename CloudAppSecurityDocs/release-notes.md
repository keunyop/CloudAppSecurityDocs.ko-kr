---
title: Cloud App Security의 새로운 기능 | Microsoft Docs
description: 이 항목은 자주 업데이트되어 Cloud App Security 최신 릴리스의 새로운 기능을 소개합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/24/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 02e1036b6ab8b4796080bb3e91007e6d2dd365ce
ms.sourcegitcommit: 8a31b9bb4594c74cf200cf81e31c0fd9d6d776a6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39220646"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="whats-new-with-microsoft-cloud-app-security"></a>Microsoft Cloud App Security의 새로운 기능

## <a name="cloud-app-security-release-128"></a>Cloud App Security 릴리스 128

릴리스 날짜: 2018년 7월 22일

-   **여러 앱에서 앱 권한 작업**<br>
앱 권한이 부여된 앱에 대해 한 번에 여러 앱을 금지하거나 승인할 수 있습니다. 예를 들어 조직의 사용자가 권한을 부여한 모든 앱을 검토하고, 금지하려는 모든 앱을 선택한 다음, 앱 금지를 클릭하고 부여된 모든 동의를 취소하여 사용자가 해당 앱에 대한 권한을 더 이상 부여할 수 없도록 할 수 있습니다.  자세한 내용은 [앱 권한 관리](manage-app-permissions.md)를 참조하세요.
-   **Azure 응용 프로그램에 대한 지원 향상**<br>
Azure의 경우 Azure 응용 프로그램(내부 및 외부 모두)에서 수행되는 사용자 계정 활동으로 응용 프로그램을 검색하는 기능이 점차적으로 출시되고 있습니다. 이를 통해 응용 프로그램에서 예기치 않게 권한이 없는 작업을 수행할 경우 이를 경고하는 정책을 만들 수 있습니다. 자세한 내용은 [Microsoft Cloud App Security에 Azure 연결](connect-azure-to-microsoft-cloud-app-security.md)을 참조하세요.
-   **새로운 GDPR 감지 유형으로 데이터 분류 엔진 업데이트**<br>
파일에서 GDPR 관련 콘텐츠를 검색할 수 있도록 [Cloud App Security 데이터 분류 서비스](dcs-inspection.md)에서 데이터 분류 엔진에 새로운 GDPR 감지 유형이 추가되었습니다.
-   **클라우드 앱 카탈로그 업데이트**<br>
현재 GDPR 준비 상태를 비롯한 데이터 프라이버시 및 소유권 규정 준수를 관리할 수 있도록 Cloud App Catalog에 법적 위험 범주 (일반, 보안 및 규정 준수 이외에)가 포함됩니다.
각 클라우드 앱의 GDPR 준비 상태를 평가하는 데 도움이 되도록, 새로운 위험 범주에 클라우드 서비스의 GDPR 준비 상태 명령문 및 각 GDPR 프레임워크 컨트롤의 상태가 포함됩니다.
이러한 기능 향상의 일환으로, 다음과 같은 위험 특성이 기타 위험 범주에서 법률 범주로 옮겨졌습니다.
     - DMCA
     - 데이터 소유권
     - 데이터 보존 정책

     또한 새로운 위험 범주가 별도로 채점되기 때문에 선호도 및 우선 순위에 따라 점수 가중치를 구성할 수 있습니다. 자세한 내용은 [위험 점수](risk-score.md)를 참조하세요.

-   **새로운 추천 쿼리: GDPR 준비** <br>
검색된 GDPR에 준비된 앱을 식별할 수 있는 새로운 추천 쿼리가 있습니다. 최근 GDPR이 보안 관리자에게 최우선 순위가 되었기 때문에 이 쿼리를 사용하면 GDPR에 준비된 앱을 쉽게 식별하고 그렇지 않은 앱의 위험을 평가하여 위협을 완화할 수 있습니다.


## <a name="cloud-app-security-release-127"></a>Cloud App Security 릴리스 127

릴리스 날짜: 2018년 7월 8일

- 이제 Office 365의 일반 작업을 **활동 로그** 및 **활동 정책**에서 볼 수 있습니다. 이제 **지정되지 않음** 작업에 대한 Office 365 작업을 필터링할 수 있습니다. 이러한 활동을 검토하면 Cloud App Security에서 분류되지 않은 수행된 동작에 대한 정보를 조사할 수 있습니다. 또한 이러한 활동을 사용하여 Cloud App Security 팀에 요청을 보내 이러한 활동에 따라 새로운 활동 유형을 생성할 수 있습니다. 

## <a name="cloud-app-security-release-126"></a>Cloud App Security 릴리스 126

릴리스 날짜: 2018년 6월 24일

-   **조건부 액세스 앱 제어 GA**<br>이제 Microsoft Cloud App Security의 조건부 액세스 앱 제어(역방향 프록시)는 모든 SAML 응용 프로그램에 대해 일반 공급됩니다. 조건부 액세스 앱 제어는 **실시간으로 사용자 세션을 모니터링하고 제어**하기 위해 Azure AD 조건부 액세스 정책을 사용하여 직접 통합되는 동시에 생산성을 높일 수 있습니다. 먼저 기능을 미리 보기하므로 다음을 비롯한 다양한 기능이 추가되고 향상되었습니다. 
    -   브라우저 트래픽에 대한 세션 정책을 만드는 작업 외에도 [액세스 정책](access-policy-aad.md)을 만들어 기본 클라이언트의 동일한 앱에 대한 액세스 권한을 관리합니다.
    -   앱 온보딩 프로세스는 조직에서 사용자 지정 SAML 응용 프로그램을 지원하도록 간소화되었습니다.
    -   Azure 전세계 네트워크의 일환으로 전 세계에 있는 모든 사용자에 대한 원활한 환경을 위해 통합 및 인터페이스가 개선되었습니다.
 

-   **Microsoft 데이터 분류 서비스 GA를 사용한 콘텐츠 검사**<br>Microsoft 데이터 분류 서비스와 Microsoft Cloud App Security 통합은 이제 일반 공급됩니다. 이 통합을 통해 기본적으로 Microsoft 데이터 분류 서비스를 활용하여 클라우드 앱의 파일을 분류할 수 있습니다. 자세한 내용은 [Microsoft 데이터 분류 서비스 통합](dcs-inspection.md)을 참조하세요. 이 기능은 현재 미국과 유럽(프랑스 제외)에서만 사용할 수 있는 기능입니다.

- **Cloud Discovery 주요 보고서**<br>Microsoft Cloud App Security는 Cloud Discovery 주요 PDF 보고서를 생성하는 기능을 롤아웃합니다. 이 보고서에서는 조직에서 식별된 섀도 IT 사용량 개요를 제공하여 전반적인 사용량 및 주요 범주의 상위 앱 및 사용자를 강조 표시하고 조직에서 섀도 IT가 갖는 위험을 중점적으로 설명합니다. 또한 보고서에서는 조직에서 섀도 IT에 대한 가시성을 개선하고 제어하는 방법에 대한 권장 사항 목록을 제공합니다. 이 보고서를 사용하여 잠재적 위험 및 위협을 제거하고 조직을 안전하게 유지하는지 확인합니다.

-   **맬웨어 검색**<br>파일 형식에 관계 없이 **클라우드 저장소에서 악성 파일을 자동으로 검색**하는 맬웨어 검색 기능은 점진적으로 롤아웃됩니다. Microsoft Cloud App Security는 Microsoft의 위협 인텔리전스를 사용하여 특정 파일이 알려진 맬웨어 공격과 연결되는지 아니면 잠재적으로 악의적인지를 인식합니다. 자세한 내용은 [변칙 검색 정책](anomaly-detection-policy.md)을 참조하세요.
 
-   **의심스러운 작업에 대한 자동 수정**<br>이제 변칙 검색 정책에 의해 트리거되는 의심스러운 세션에 대해 자동 수정 작업을 설정할 수 있습니다. 이 향상된 기능을 사용하면 위반이 발생하고 사용자 일시 중단과 같은 **거버넌스 작업을 자동으로 적용**할 때 즉시 경고할 수 있습니다. 자세한 내용은 [변칙 검색 정책](anomaly-detection-policy.md#adp-automated-gov)을 참조하세요. 
 
-   **Azure에 대한 보안 구성 평가**<br>Microsoft Cloud App Security는 점진적으로 Azure 환경의 보안 구성 평가를 사용하는 기능을 롤아웃하고, 누락된 구성 및 보안 제어에 대한 권장 사항을 제공합니다. 예를 들어 관리자에 대한 MFA를 누락한 경우 알림을 표시합니다. 자세한 내용은 [클라우드 보안 상태 관리 통합](security-config.md)을 참조하세요.  
  
-   **위험한 OAuth 앱 자동 감지**<br>환경에 연결된 OAuth 앱의 기존 조사 외에도 Microsoft Cloud App Security는 이제 점진적으로 OAuth 앱이 특정 기준을 충족하는 경우 알 수 있도록 자동화된 알림을 설정하는 기능을 롤아웃합니다. 예를 들어 높은 사용 권한 수준이 필요하고 50명을 초과하는 사용자에 의해 권한이 부여된 앱이 있는 경우 자동으로 경고를 받을 수 있습니다. 자세한 내용은 [앱 사용 권한 정책](app-permission-policy.md)을 참조하세요.
 
-   **MSSP(관리되는 보안 서비스 공급자) 관리 지원**<br>Microsoft Cloud App Security는 이제 MSSP에 더 나은 관리 환경을 제공합니다. 외부 사용자는 이제 관리자로 구성되고 [Microsoft Cloud App Security에서 현재 지원되는 역할](manage-admins.md) 중 하나를 할당받을 수 있습니다. 또한 여러 고객 테넌트에 서비스를 제공하는 데 MSSP를 사용하기 위해 둘 이상의 테넌트에 대한 액세스 권한이 있는 관리자는 포털 내에서 테넌트를 쉽게 전환할 수 있습니다. 관리자를 관리하는 방법에 대한 자세한 내용은 [관리자 관리](manage-admins.md)를 참조하세요.
  
-   **외부 DLP GA와 통합**<br>Microsoft Cloud App Security를 사용하여 DLP(데이터 손실 방지) 솔루션과 같은 [타사 분류 시스템에서 기존 투자를 활용](icap-stunnel.md)할 수 있고 사용자 환경에서 실행되는 기존 배포를 사용하여 클라우드 응용 프로그램의 콘텐츠를 검색할 수 있습니다. 자세한 내용은 [외부 DLP 통합](icap-stunnel.md)을 참조하세요.


## <a name="cloud-app-security-release-125"></a>Cloud App Security 릴리스 125

릴리스 날짜: 2018년 6월 10일


- **새로운 상위 사용자별 조사 기능:**<br>
Microsoft Cloud App Security에서는 열린 위협 검색 경고 수를 기준으로 상위 사용자를 표시하는 새로운 조사 위젯이 대시보드에 추가되었습니다. 이 조사 위젯을 사용하면 의심스러운 세션 수가 가장 큰 사용자에 대한 위협 조사에 집중할 수 있습니다.

- **AWS S3 버킷에 대한 지원:**<br>
Microsoft Cloud App Security는 이제 AWS S3 버킷 및 해당 공유 수준을 검색할 수 있습니다. 이 기능은 공개적으로 액세스할 수 있는 AWS 버킷에 대한 경고 및 가시성을 제공합니다. 또한 버킷을 기반으로 정책을 만들고 자동 거버넌스를 적용할 수 있습니다. 또한 AWS 저장소를 제어하기 위한 정책을 쉽게 만드는 데 사용할 수 있는 **공개적으로 액세스할 수 있는 S3 버킷(AWS)** 이라는 새 정책 템플릿이 있습니다. 이러한 새 기능을 사용하려면 [AWS 연결](connect-aws-to-microsoft-cloud-app-security.md)에 설명된 새 권한을 추가하여 AWS에 연결된 앱을 업데이트해야 합니다.

- **사용자 그룹에 따른 관리자 권한**: 이제 사용자 그룹별 Microsoft Cloud App Security 관리자의 관리 권한을 설정할 수 있습니다. 예를 들어, 특정 사용자를 독일에 있는 사용자 전용 관리자로 설정할 수 있습니다. 이렇게 하면 사용자가 “독일 - 모든 사용자” 사용자 그룹에 대해서만 Microsoft Cloud App Security에서 정보를 보고 수정할 수 있습니다. 자세한 내용은 [관리자 액세스 관리](manage-admins.md)를 참조하세요.


## <a name="cloud-app-security-release-124"></a>Cloud App Security 릴리스 124

릴리스 날짜: 2018년 5월 27일

-   **클라우드 앱 카탈로그에 GDPR 위험 평가가 추가됨**<br>
13개의 새로운 위험 요인이 Microsoft Cloud App Security에 추가되었습니다. 이러한 위험 요인은 GDPR 프레임워크의 검사 목록을 따르는 것으로, GDPR 규정에 따라 클라우드 앱 카탈로그의 앱을 평가할 수 있도록 하는 것입니다.

-   **Microsoft 데이터 분류 서비스와 통합**<br>
이제 Microsoft Cloud App Security를 통해 기본적으로 Microsoft 데이터 분류 서비스를 활용하여 클라우드 앱의 파일을 분류할 수 있습니다. <br>
Microsoft 데이터 분류 서비스는 Office 365, Azure Information Protection 및 Microsoft Cloud App Security에서 통합 정보 보호 환경을 제공합니다. 따라서 같은 데이터 분류 프레임워크를 Microsoft Cloud App Security로 보호되는 타사 클라우드 앱으로 확장하여 훨씬 더 많은 수의 앱에서 이미 한 결정을 활용할 수 있습니다. 

-   **Microsoft Azure에 연결**(점진적 출시)<br>
Microsoft Cloud App Security는 해당 IaaS 모니터링 기능을 Amazon Web Services 이상으로 확장하고 있으며 현재는 Microsoft Azure를 지원합니다. 따라서 Cloud App Security를 사용하여 모든 Azure 구독을 원활하게 연결하고 모니터링할 수 있습니다. 이 연결은 다음을 비롯하여 Azure 환경을 보호할 수 있는 강력한 도구 집합을 제공합니다. 

       -    포털을 통해 수행된 모든 활동 파악

       -    원치 않는 동작에 대해 경고하도록 하는 사용자 지정 정책을 만드는 기능 및 있을 수 있는 위험한 사용자를 일시 중단하거나 강제로 다시 로그인하도록 하여 위험한 사용자를 자동으로 방지하는 기능

       -    모든 Azure 활동은 변칙 검색 엔진으로 검사되고 Azure Portal에서 의심스러운 동작(예: 불가능한 이동, 의심스러운 대량 활동 및 새로운 국가에서의 활동)에 대해 자동으로 경고합니다.<br>

  자세한 내용은 [Microsoft Cloud App Security에 Azure 연결](connect-azure-to-microsoft-cloud-app-security.md)을 참조하세요.
 
-   **범위 지정 배포**(점진적 출시) <br>
Microsoft Cloud App Security는 그룹 구성원 자격을 기반으로 모니터링하고 보호할 사용자를 세부적으로 결정하는 기능을 엔터프라이즈에 제공합니다. 이 기능을 사용하면 보호된 응용 프로그램에 대해 활동이 표시되지 않는 사용자를 선택할 수 있습니다. 범위 지정 모니터링 기능은 특히 다음 경우에 유용합니다. 

    -   준수 - 준수 규정에서 현지 규정으로 인해 특정 국가의 사용자를 모니터링하지 않도록 요구하는 경우

       -    라이선스 - Microsoft Cloud App Security 라이선스 제한을 준수하기 위해 더 적은 수의 사용자를 모니터링하려는 경우.
   자세한 내용은 [범위 지정 배포](scoped-deployment.md)를 참조하세요.

-   **검색된 앱에 대한 위반 앱 경고**<br>
 이제 테넌트의 검색된 앱이 위반했을 때 알려주는 기본 제공 경고가 있습니다. 경고는 위반 날짜 및 시간, 앱을 사용한 사용자 및 위반에 대한 정보를 제공하는 공개적으로 사용할 수 있는 소스의 링크에 대한 정보를 제공합니다.

-   **새 메일 서버**<br>
 Cloud App Security의 메일 서버가 변경되었으며 다른 IP 주소 범위를 사용합니다. 알림을 받으려면 새 IP 주소를 스팸 방지 허용 목록에 추가합니다. 알림을 사용자 지정하려는 사용자의 경우 Microsoft Cloud App Security에서 타사 메일 서비스인 MailChimp®를 사용하여 사용자를 위해 사용자 지정해 줍니다. 메일 서버 IP 주소 목록 및 MailChimp를 사용하기 위한 지침은 [네트워크 요구 사항](https://docs.microsoft.com/cloud-app-security/network-requirements#email-server) 및 [메일 설정](mail-settings.md)을 참조하세요.


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

-   Office 365 및 Azure AD를 위해 현재 Office 365 및 Azure AD 응용 프로그램(내부 및 외부 모두)에서 수행되는 사용자 계정 활동으로 내부 응용 프로그램을 검색하는 기능을 점진적으로 출시하고 있습니다. 이를 통해 응용 프로그램에서 예기치 않게 권한이 없는 작업을 수행할 경우 이를 경고하는 정책을 만들 수 있습니다. 
-   앱 권한 목록을 csv로 내보낼 때 준수 및 조사 프로세스를 지원하기 위해 게시자, 권한 수준 및 커뮤니티 사용량과 같은 추가 필드가 포함됩니다.
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

- 이제 사용자 및 IP 주소 페이지의 검색 기능을 사용하면 자동 완성을 통해 원하는 내용을 더 쉽게 찾을 수 있습니다.

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
  
  