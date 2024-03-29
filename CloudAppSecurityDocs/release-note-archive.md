---
title: Cloud App Security의 이전 업데이트 아카이브
description: 이 문서는 Cloud App Security의 이전 릴리스에서 만들어졌던 업데이트를 설명하는 아카이브입니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 185c3a46-ede8-4d58-b232-111807845c8f
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 30cf7145006156cddce444fb2365f8691fe3eb07
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568586"
---
# <a name="past-release-archive-of-microsoft-cloud-app-security"></a>Microsoft Cloud App Security의 이전 릴리스 아카이브

*적용 대상: Microsoft Cloud App Security*

이 문서는 Cloud App Security의 이전 릴리스에서 만들어졌던 업데이트를 설명하는 아카이브입니다. 최신 새로운 기능 목록을 보려면 [Cloud App Security의 새로운 기능](release-notes.md)을 참조하세요.

## <a name="updates-made-in-2017"></a>2017년의 업데이트

### <a name="cloud-app-security-release-113"></a>Cloud App Security 릴리스 113

릴리스 날짜: 2017년 12월 25일

- 이제 Cloud App Security에서 Azure Information Protection과의 심층적인 통합이 지원됩니다. 공개 미리 보기 기능을 사용하면 클라우드 앱에서 파일을 검색 및 분류할 수 있고 Azure Information Protection 레이블을 자동으로 적용하여 보호할 수 있습니다. 이 기능은 Box, SharePoint 및 OneDrive에서 사용할 수 있습니다. 자세한 내용은 [Azure Information Protection 통합](azip-integration.md)을 참조하세요.

- 이제 Cloud Discovery 로그 파서는 다음과 같은 일반 형식을 지원합니다. LEEF, CEF 및 W3C


### <a name="cloud-app-security-release-112"></a>Cloud App Security 릴리스 112

2017년 12월 10일에 릴리스됨

- 이제 활동 로그에서 사용자 이름 또는 IP 주소를 클릭하여 관련된 정보 서랍에 액세스할 수 있습니다. 
- 이제 활동을 조사할 때 시계 아이콘을 클릭하여 인사이트 서랍에서 동일한 기간 내의 모든 활동을 쉽게 볼 수 있습니다. 시계 아이콘을 사용하면 보고 있는 활동의 48시간 이내에 수행된 모든 작업을 볼 수 있습니다.
- Juniper SRX에 대한 Cloud Discovery 로그 파서의 성능이 향상되었습니다.
- 프록시에 의해 모니터링되는 활동의 경우, **활동 개체**가 DLP 검사와 관련된 정보를 포함하도록 확장되었습니다. 일치하는 정책이 있는 경우 DLP 위반을 포함하도록 확장 되었습니다.


### <a name="cloud-app-security-release-111"></a>Cloud App Security 릴리스 111

2017년 11월 26일 출시됨

- 이제 검색 정책은 앱 태그를 조건 및 거버넌스 작업으로 지원합니다. 이 추가 기능을 사용하면 새로 검색된 앱에 **인기 앱**과 같은 사용자 지정 태그를 자동으로 지정할 수 있습니다. 앱 태그를 필터로 사용할 수도 있습니다. 예를 들어 “하루에 ‘관심 목록’의 앱을 사용하는 사용자가 100명이 넘을 경우에 경고합니다”.

- **시간** 필터가 더 사용자에게 친숙하도록 개선되었습니다.

- 이제 콘텐츠 검사를 통해 콘텐츠, 메타데이터 및 파일 이름을 구별할 수 있으므로 검사할 항목을 선택할 수 있습니다.

- G Suite에 대한 새 거버넌스 작업이 추가되었습니다. 이제 공유 파일에 대한 **공용 액세스를 줄일** 수 있습니다. 이 작업을 통해 공개적으로 사용할 수 있는 파일을 공유 링크에서만 사용할 수 있도록 설정할 수 있습니다.

- 다른 애플리케이션에 대한 모든 OKTA 로그온 활동은 이제 OKTA에서 시작되는 것으로 Cloud App Security에 표시됩니다. 활동의 **활동 개체** 필드에서 로그인이 수행된 대상 애플리케이션을 기반으로 보고 필터링할 수 있습니다.


### <a name="cloud-app-security-release-110"></a>Cloud App Security 릴리스 110

2017년 11월 12일 출시됨

- 현재 일반 공급: 로그 수집기에 대한 새 배포 모드를 출시하기 시작했습니다. 현재 가상 어플라이언스 기반 배포 이외에 새로운 Docker(컨테이너) 기반 로그 수집기를 패키지로 [Ubuntu 컴퓨터](discovery-docker.md)에 온-프레미스 및 Azure를 사용하여 설치할 수 있습니다. Docker를 사용할 경우 호스팅 컴퓨터는 이를 자유롭게 패치 및 모니터링할 수 있는 고객이 소유합니다.

- 모서리에 있는 새 파란색 물음표를 사용하여 포털의 페이지 내에서 docs.microsoft.com의 관련 Cloud App Security 설명서 페이지에 액세스할 수 있습니다. 각 링크는 컨텍스트에 따라 표시되므로 현재 페이지에 따라 필요한 정보로 이동합니다.
- 이제 Cloud App Security 포털의 모든 페이지에서 피드백을 보낼 수 있습니다. 피드백을 통해 버그를 보고하고 새 기능을 요청하며 Cloud App Security 팀과 직접 공유할 수 있습니다.
- 클라우드 검색 기능이 향상되어 조직의 클라우드 사용 현황을 심층 조사하기 위한 하위 도메인 인식이 가능합니다. 자세한 내용은 [검색된 앱 사용](discovered-apps.md)을 참조하세요.

### <a name="cloud-app-security-release-109"></a>Cloud App Security 릴리스 109

릴리스 날짜: 2017년 10월 29일 

- Microsoft Cloud App Security 프록시 기능 출시가 시작했습니다. Microsoft Cloud App Security 프록시는 클라우드 환경에 대한 액세스 및 클라우드 환경 내의 활동에 대한 실시간 가시성 및 제어가 필요한 도구를 제공합니다. 예:

  - 다운로드를 시작하기 전에 차단하여 데이터 누수를 미리를 방지합니다.
  - 클라우드에서 저장되거나 다운로드한 데이터를 암호화로 보호하도록 적용하는 규칙을 설정합니다.
  - 보호되지 않는 엔드포인트에 대한 가시성을 확보하여 관리되지 않는 디바이스에서 수행되는 작업을 모니터링할 수 있습니다.
  - 비회사 네트워크 또는 위험한 IP 주소로부터의 액세스를 제어합니다.
  
  자세한 내용은 [조건부 액세스 앱 제어로 앱 보호](proxy-intro-aad.md)를 참조하세요.

- 특정 서비스 활동 이름에 따라 필터링하는 기능을 점진적으로 배포하고 있습니다. 이 새로운 활동 유형 필터는 자세히 세분화되어 있어 매우 일반적인 활동 유형과 달리 특정 앱 활동을 모니터링할 수 있습니다. 예를 들어 이전에는 **실행 명령**을 필터링할 수 있었고, 이제는 특정 EXO cmdlet을 필터링할 수 있습니다. 활동 이름은 **유형(앱)** 의 [활동] 서랍에서도 확인할 수 있습니다. 이 기능은 결국 활동 유형 필터를 바꿉니다.  

- 클라우드 검색에서는 이제 Cisco ASA with FirePOWER를 지원합니다. 

- 사용자 환경을 개선하기 위해 Discovery 사용자 및 IP 페이지의 성능이 향상되었습니다.

### <a name="cloud-app-security-releases-105-106-107-108"></a>Cloud App Security 릴리스 105, 106, 107, 108

릴리스 날짜: 2017년 9/10월

- Cloud App Security에는 이제 EU에 있는 데이터 센터가 포함됩니다. Cloud App Security 고객은 미국 데이터 센터 외에도 EU 데이터 센터를 통해 예정된 새로운 유럽 표준 및 인증을 완벽하게 준수할 수 있습니다.
- 더 간단한 필터링과 추가 통찰력을 제공하는 새 필터가 **App 커넥터** 페이지에 추가되었습니다.
- 대상 IP 정보만 있는 로그 파일에 대한 클라우드 검색이 향상되었습니다.

### <a name="cloud-app-security-release-104"></a>Cloud App Security 릴리스 104 

릴리스 날짜: 2017년 8월 27일

- 이제 **IP 주소 범위 API**를 사용하여 스크립트를 만들어 IP 범위를 대량으로 추가할 수 있습니다. API에서 물음표를 클릭한 다음, **API 설명서**를 클릭하여 Cloud App Security 포털 메뉴 모음에서 찾을 수 있습니다.
- Cloud Discovery는 이제 차단된 트랜잭션뿐만 아니라 전체 트랜잭션을 제공하여 차단된 트랜잭션에 대해 더 향상된 가시성을 제공합니다.
- 이제 **ISO 27017** 인증 여부를 기준으로 클라우드 애플리케이션을 필터링할 수 있습니다. 이 새로운 클라우드 앱 카탈로그 위험 요소는 애플리케이션 공급자가 이 인증을 보유하고 있는지 여부를 확인합니다. ISO 27017은 공용 클라우드 컴퓨팅 환경에서 사용자 정보를 처리하고 보호하기 위해 통상적으로 준수하는 제어 및 지침을 확립합니다.
- GDPR 규정 준수에 대한 준비를 활성화하기 위해 클라우드 앱 카탈로그의 클라우드 앱에서 GDPR 준비 문을 수집했습니다. 앱 위험 점수에 아직 영향을 주지 않지만 제공되는 경우 앱 게시자의 GDPR 준비 페이지에 대한 링크를 제공합니다. Microsoft는 이 콘텐츠를 확인하지 않았으며 해당 유효성에 대한 책임이 없습니다.

### <a name="cloud-app-security-release-103"></a>Cloud App Security 릴리스 103 

릴리스 날짜: 2017년 8월 13일

- Cloud App Security에 .docm, .docx, .dotm, .dotx, .xlam, .xlsb, .xlsm, .xlsx, .xltx, .xps, .potm, .potx, .ppsx, .ppsm, .pptm, .pptx, .thmx, .vsdx, .vsdm, .vssx, .vssm, .vstx, .vstm과 같은 Office 파일을 위한 Azure Information Protection 네이티브 보호가 추가되었습니다(일반 보호 대체).

- 모든 Azure Active Directory 준수 관리자는 Cloud App Security에서 유사한 권한을 자동으로 부여받습니다. 사용 권한에는 읽기 전용, 경고 관리, 파일 정책 생성 및 수정, 파일 거버런스 작업 허용 및 데이터 관리에서 모든 기본 제공 보고서 보기에 대한 기능을 포함됩니다. 

- 위반 컨텍스트를 더 잘 이해할 수 있도록 DLP 위반 컨텍스트를 40자에서 100자로 확장했습니다.

- 로그 업로드 오류를 쉽게 해결할 수 있도록 상세한 오류 메시지가 Cloud Discovery Custom Log 업로더로 전송됩니다.

- Zscaler 형식을 지원하기 위해 Cloud Discovery 블록 스크립트가 확장되었습니다.

- 새로운 클라우드 앱 카탈로그 위험 요소: 계정 종료 후 데이터 보존. 이 위험 요소를 사용하면 클라우드 앱 내에서 계정이 종료된 후 데이터가 완전히 제거되었는지 확인할 수 있습니다.

### <a name="cloud-app-security-release-102"></a>Cloud App Security 릴리스 102

릴리스 날짜: 2017년 7월 30일

- IP 주소 정보는 거의 모든 조사에 매우 중요하므로 이제 활동 서랍에서 IP 주소에 대한 자세한 정보를 볼 수 있습니다. 특정 활동 내에서 이제 IP 주소 탭을 클릭하면 IP 주소에 대한 통합 데이터를 볼 수 있습니다. 데이터에는 특정 IP 주소에 대해 미해결 경고의 수, 최근 활동의 추세 그래프 및 위치 맵이 포함됩니다. 이 기능을 통해 쉽게 드릴다운할 수 있습니다. 예를 들어 불가능한 이동 경고를 조사할 때 IP 주소가 어디에 사용되었는지와 의심스러운 활동과 관련되어 있는지를 쉽게 알 수 있습니다. IP 주소를 위험, VPN 또는 회사로 지정할 수 있게 하는 IP 주소 서랍에서 작업을 바로 수행함으로써 향후 조사와 정책 만들기를 쉽게 수행할 수 있습니다. 자세한 내용은 [IP 주소 인사이트](activity-filters.md#ip-address-insights)를 참조하세요.

- Cloud Discovery에서 이제 [자동화된 로그 업로드](discovery-docker.md)에 [사용자 지정 로그 형식](custom-log-parser.md)을 사용할 수 있습니다. 사용자 지정 형식을 사용하면 Splunk 서버 또는 기타 지원되지 않는 형식과 같은 SIEM에서 로그 업로드를 쉽게 자동화할 수 있습니다.

- 새 사용자 조사 작업은 사용자 조사에 추가된 수준의 드릴다운을 사용할 수 있게 합니다. **조사** 페이지에서 이제 작업, 사용자 또는 계정을 마우스 오른쪽 단추로 클릭하고 고급 조사 및 필터링에 대해 다음 새 필터 중 하나를 적용할 수 있습니다. **관련 활동 보기**, **관련 거버넌스 보기**, **관련 경고 보기**, **소유한 파일 보기**, **이 사용자와 공유한 파일 보기**

- 클라우드 앱 카탈로그에는 이제 계정 종료 후 데이터 보존의 새로운 필드가 포함되어 있습니다. 이 위험 요소를 사용하면 클라우드 앱 내에서 계정이 종료된 후 데이터가 완전히 제거되었는지 확인할 수 있습니다.

- 이제 Cloud App Security를 통해 Salesforce 개체와 관련된 활동에 대한 가시성을 향상시켰습니다. 개체에는 잠재 고객, 계정, 캠페인, 기회, 프로필 및 사례가 포함됩니다. 예를 들어 계정 페이지 액세스에 대한 가시성을 사용하면 어떤 사용자가 비정상적으로 많은 수의 계정 페이지를 볼 경우 나에게 경고 메시지를 전달하도록 정책을 구성할 수 있습니다. 이는 Salesforce에서 Salesforce Event Monitoring(Salesforce Shield의 일부)을 사용하도록 설정한 경우에 Salesforce App Connector를 통해 가능합니다.

- 이제 비공개 미리 보기 고객이 Do Not Track을 사용할 수 있습니다! 이제 어느 사용자의 활동 데이터를 처리할지 제어할 수 있습니다. 이 기능을 사용하면 Cloud App Security에서 특정 그룹을 "Do not track(추적 안 함)"으로 설정할 수 있습니다. 예를 들어 이제는 독일이나 특정 규정 준수 규칙으로 바인딩되지 않은 국가에 위치한 사용자의 활동 데이터를 처리할지를 결정할 수가 있습니다. 이는 특정 앱과 특정 하위 앱 등 Cloud App Security의 모든 앱에 걸쳐 구현할 수 있습니다. 또한, 이 기능을 사용하면 Cloud App Security의 단계적 롤아웃을 수행할 수 있습니다. 자세한 내용을 보거나 이 기능의 비공개 미리 보기에 참가하려면 지원 또는 계정 담당자에게 문의하세요. 

### <a name="cloud-app-security-release-100"></a>Cloud App Security 릴리스 100

릴리스 날짜: 2017년 7월 3일

**새로운 기능**

- **보안 확장:** 보안 확장은 Cloud App Security에 대한 모든 보안 확장의 중앙 집중식 관리를 위한 새 대시보드입니다.  확장에는 API 토큰 관리, SIEM 에이전트 및 외부 DLP 커넥터가 포함됩니다. 새 대시보드는 Cloud App Security의 “설정”에서 사용할 수 있습니다. 

    - API 토큰 – 고유한 [API 토큰](api-tokens.md)을 생성하고 관리하여 RESTful API를 통해 Cloud App Security를 타사 소프트웨어와 통합합니다. 
    - SIEM 에이전트 – [SIEM 통합](siem.md)은 이전에 “설정” 바로 아래에 있었지만 이제는 보안 확장의 탭으로 사용할 수 있습니다.
    - 외부 DLP(미리 보기) – Cloud App Security를 사용하여 DLP(데이터 손실 방지) 솔루션과 같은 [타사 분류 시스템에서 기존 투자를 활용](icap-stunnel.md)할 수 있고 사용자 환경에서 실행되는 기존 배포를 사용하여 클라우드 애플리케이션의 콘텐츠를 검색할 수 있습니다. 미리 보기에 가입하려면 계정 관리자에게 문의하세요.

- **자동 사용 권한 부여/취소:** 새 앱 검색 정책은 Cloud Discovery에 사용 권한/비사용 권한 레이블이 있는 앱을 자동으로 설정하는 기능을 제공합니다. 이 기능을 통해 조직 정책 및 규정을 위반한 앱을 자동으로 식별하고, 이러한 앱을 생성된 차단 스크립트에 추가할 수 있습니다.
- **Cloud App Security 파일 레이블:** 이제 Cloud App Security 파일 레이블을 적용하여 검색하는 파일에 대한 더 많은 인사이트를 제공할 수 있습니다. Cloud App Security DLP가 검색한 각 파일에 대해 파일이 암호화되거나 손상되어 검사가 차단되었는지 알 수 있습니다. 예를 들어 외부에서 공유되는 암호로 보호된 파일에 대해 경고하고 이를 격리하는 정책을 설정할 수 있습니다. 이 기능은 2017년 7월 3일 이후 검색된 파일에 사용할 수 있습니다.

    필터 **분류 레이블** > **Cloud App Security**를 사용하여 이러한 파일을 필터링할 수 있습니다. 

  - **Azure RMS로 암호화** – 파일에 Azure RMS 암호가 설정되어 있어 해당 콘텐츠가 검사되지 않은 파일입니다.
  - **암호로 암호화** – 파일이 사용자에 의해 암호로 보호되어 해당 콘텐츠가 검사되지 않은 파일입니다.
  - **손상 파일** – 파일 콘텐츠를 읽을 수 없어 해당 콘텐츠가 검사되지 않은 파일입니다.

- **사용자 정보**: 작업 사용자에 대한 기본 제공 정보를 사용할 수 있도록 조사 환경이 업그레이드되었습니다. 한 번 클릭으로 활동 서랍에서 사용자의 포괄적인 개요를 볼 수 있으며, Insights에는 사용자가 연결이 시작된 위치, 사용자가 관련된 열린 경고 수 및 메타데이터 정보가 포함되어 있습니다.
- **앱 커넥터 정보:** **앱 커넥터**에서 각 연결된 앱에는 이제 상태를 더 쉽게 드릴다운할 수 있는 앱 서랍이 표에 포함됩니다. 제공되는 세부 정보에는 앱 커넥터가 연결된 시간 및 커넥터에 대한 마지막 상태 검사가 포함됩니다. 각 앱에서 DLP 및 실시간 검색(요청된 검색 및 실제 검색)의 상태에서 검사된 총 파일 수와 같은 DLP 검색 상태를 모니터링할 수도 있습니다. Cloud App Security에서 실시간으로 검색한 파일의 비율이 요청된 수보다 낮은지 여부와 테넌트가 용량을 초과하여 DLP 결과에서 지연을 경험하는지 여부를 알릴 수 있습니다.

- **클라우드 앱 카탈로그 사용자 지정:**

  - **앱 태그**: 이제 앱에 대한 사용자 지정 태그를 만들 수 있습니다. 이러한 태그는 조사하려는 앱의 특정 유형을 심층 분석하기 위한 필터로 사용할 수 있습니다. 예를 들어 사용자 지정 조사 목록, 특정 비즈니스 단위에 대한 지정 또는 사용자 지정 승인(예: “법적 승인”)을 사용할 수 있습니다.
  - **사용자 지정 메모**: 환경에서 검색된 다양한 애플리케이션을 검토하고 평가할 때 결론 및 정보를 메모에 저장할 수 있습니다.
  - **사용자 지정 위험 점수**: 앱의 위험 점수를 재정의할 수 있습니다. 예를 들어 앱의 위험 점수가 8이고 해당 앱이 조직에서 사용 권한 앱인 경우 조직에 대한 위험 점수를 10으로 변경할 수 있습니다. 메모를 추가하여 누군가 앱을 검토할 때 변경의 근거를 분명히 설명할 수도 있습니다.

- **새 로그 수집기 배포 모드:** 배포를 시작하면서 이제 새로운 배포 모드를 로그 수집기에 사용할 수 있습니다. 현재 가상 어플라이언스 기반 배포 이외에 새로운 Docker(컨테이너) 기반 로그 수집기를 패키지로 Windows 및 Ubuntu 컴퓨터에 온-프레미스 및 Azure를 사용하여 설치할 수 있습니다. Docker를 사용할 경우 호스팅 컴퓨터는 이를 자유롭게 패치 및 모니터링할 수 있는 고객이 소유합니다.

**알림:**

- 클라우드 앱 카탈로그는 이제 15,000개 이상의 검색 가능한 앱을 지원합니다.
- 규정 준수: Cloud App Security는 Azure에서 공식적으로 SOC1/2/3 인증을 했습니다. 전체 인증 목록을 보려면 [규정 준수 제안](https://www.microsoft.com/trustcenter/compliance/complianceofferings)을 참조하거나 Cloud App Security 결과를 필터링하세요.

**기타 향상된 기능:** 

- **향상된 구문 분석:** Cloud Discovery 로그 구문 분석 메커니즘에서 기능이 향상되었습니다. 내부 오류 발생 가능성이 크게 감소했습니다.
- **예상 로그 형식:** Cloud Discovery 로그에 대한 예상 로그 형식이 Syslog 형식 및 FTP 형식에 대한 예제를 제공합니다.
- **로그 수집기 업로드 상태:** 포털에서 로그 수집기 상태를 확인하고 포털 내 상태 알림 및 시스템 경고를 사용하여 오류를 더 신속하게 해결할 수 있습니다.

### <a name="cloud-app-security-release-99"></a>Cloud App Security 릴리스 99

릴리스 날짜: 2017년 6월 18일

**새로운 기능**

- 이제 사용자가 모든 Office 365 및 Azure AD 앱에 다시 로그인하도록 요구할 수 있습니다. 의심스러운 사용자 활동 경고 및 손상된 계정을 빠르고 효과적으로 해결하려면 다시 로그인해야 합니다. 정책 설정 및 경고 페이지의 [사용자 일시 중단] 옵션 옆에서 새 거버넌스를 찾을 수 있습니다.
- 활동 로그에서 **가장 역할 할당 추가** 활동을 필터링할 수 있습니다. 이 활동을 사용하여 관리자는 cmdlet **New-ManagementRoleAssignment**를 사용하여 사용자 또는 시스템 계정에 **애플리케이션 가장** 역할을 지정한 시간을 검색할 수 있습니다. 이 역할을 가진 가장자는 가장자 계정과 연결된 사용 권한이 아니라 가장된 계정과 연결된 사용 권한을 사용하여 작업을 수행할 수 있습니다.
  
**Cloud Discovery 향상된 기능:**

- Azure Active Directory 사용자 이름 데이터를 사용하여 Cloud Discovery 데이터를 보강할 수 있습니다. 이 기능을 사용하도록 설정하면 검색 트래픽 로그에 수신된 사용자 이름이 Azure AD 사용자 이름과 일치하고 대체됩니다. 강화를 통해 다음과 같은 새로운 기능을 사용할 수 있습니다.
  - Azure Active Directory 사용자에 의한 섀도 IT 사용량을 조사할 수 있습니다.
  - 검색된 클라우드 앱 사용을 API로 수집된 활동과 상호 연결할 수 있습니다.
  - Azure AD 사용자 그룹을 기반으로 사용자 지정 로그를 만들 수 있습니다. 예를 들어 특정 마케팅 부서에 대한 섀도 IT 보고서를 만들 수 있습니다.
- Juniper syslog 파서의 기능이 향상되었습니다. 이제 welf 및 sd-syslog 형식을 지원합니다.
- 애플리케이션 검색을 개선하기 위해 Palo Alto 파서의 기능이 향상되었습니다.
- 로그가 성공적으로 업로드되는지 확인하기 위해 Cloud App Security 포털에서 로그 수집기의 상태를 확인할 수 있습니다. 

**일반적인 향상된 기능:**

- 이제 기본 제공 IP 주소 태그 및 사용자 지정 IP 태그는 계층 구조로 고려되고, 사용자 지정 IP 태그가 기본 제공 IP 태그보다 우선합니다. 예를 들어 IP 주소를 위협 인텔리전스에 따라 **위험**으로 태그 지정하지만 **회사**로 식별하는 사용자 지정 IP 태그가 있는 경우, 사용자 지정 범주 및 태그가 우선순위로 적용됩니다.

### <a name="cloud-app-security-release-98"></a>Cloud App Security 릴리스 98

릴리스 날짜: 2017년 6월 4일
 
**Cloud Discovery 업데이트:**

- 사용자는 이제 검색된 앱에 대해 고급 필터링을 수행할 수 있습니다. 필터링을 통해 심층 조사를 수행할 수 있습니다. 예를 들어, 사용량을 기준으로 앱을 필터링 합니다. 특정 유형의 검색된 앱에서 트래픽을 얼마나 업로드하나요? 얼마나 많은 사용자가 검색된 앱의 특정 범주를 사용하나요? 왼쪽 패널에서 다중 선택을 수행하여 여러 범주를 선택할 수도 있습니다. 
- “비규격 클라우드 스토리지 앱”과 같은 인기 검색을 기반으로 Cloud Discovery에 대한 새 템플릿 배포가 시작되었습니다. 이러한 기본 필터를 템플릿으로 사용하여 검색된 앱에서 분석을 수행할 수 있습니다.
- 쉽게 사용할 수 있도록 이제 하나의 작업으로 여러 앱에서 사용 권한 부여 및 취소 등의 작업을 할 수 있습니다.
- 이제 Azure Active Directory 사용자 그룹을 기반으로 사용자 지정 검색 보고서를 만드는 기능을 배포하고 있습니다. 예를 들어 마케팅 부서의 클라우드 사용을 확인하려면 사용자 그룹 가져오기 기능을 사용하여 마케팅 그룹을 가져온 다음, 이 그룹에 대한 사용자 지정 보고서를 만들면 됩니다.

**새로운 기능:**

- 보안 독자용 RBAC가 배포를 완료했습니다. 이 기능을 사용하여 관리자에게 부여한 사용 권한을 Cloud App Security 콘솔 내부에서 관리할 수 있습니다. 기본적으로 모든 Azure Active Directory 관리자, Office 365 글로벌 관리자 및 보안 관리자는 포털에서 모든 권한을 가집니다. Azure Active Directory 및 Office 365의 모든 보안 readers는 Cloud App Security에서 읽기 전용 액세스 권한을 가집니다. “액세스 관리” 옵션을 사용하여 관리자를 추가하거나 사용 권한을 재정의할 수 있습니다. 자세한 내용은 [관리자 권한 관리](manage-admins.md)를 참조하세요.
- 이제 Microsoft intelligent security 그래프에서 검색된 위험한 IP 주소에 대한 자세한 위협 인텔리전스 보고서를 배포하고 있습니다. 활동이 봇네트에 의해 수행되면 특정 봇네트에 대한 자세한 보고서에 연결되는 링크와 함께 봇네트의 이름(있는 경우)을 볼 수 있습니다.
 
### <a name="cloud-app-security-release-97"></a>Cloud App Security 릴리스 97

릴리스 날짜: 2017년 5월 24일

**새로운 기능:**

- 파일 및 정책 위반 조사: 이제 파일 페이지에서 모든 정책 일치를 볼 수 있습니다. 또한 파일 경고 페이지가 개선되어 특정 파일의 기록에 대한 별도의 탭이 포함되었습니다. 개선을 통해 특정 파일에 대한 모든 정책에서 위반 기록을 드릴다운할 수 있습니다. 모든 기록 이벤트에는 경고 발생 시의 파일 스냅숏이 포함됩니다. 여기에는 파일이 삭제 또는 격리되었는지 여부가 표시됩니다.
- 이제 전용 미리 보기에서 [관리자 격리](use-case-admin-quarantine.md)를 Office 365 SharePoint 및 비즈니스용 OneDrive 파일에 사용할 수 있습니다. 이 기능을 사용하면 정책과 일치하는 파일을 격리하거나 자동화된 작업을 설정하여 파일을 격리할 수 있습니다. 격리는 사용자의 SharePoint 디렉터리에서 파일을 제거하고 선택한 관리자 격리 위치에 원본을 복사합니다.

**Cloud Discovery 향상된 기능:**

- Cisco Meraki 로그에 대한 Cloud Discovery 지원이 향상되었습니다.
- Cloud Discovery에 대한 향상된 기능을 제안하는 옵션을 통해 새 위험 요인을 제안할 수 있습니다.
- 시간 및 날짜 설정을 분리하여 로그 형식을 지원하고 타임스탬프를 설정하는 옵션을 제공하도록 사용자 지정 로그 파서가 향상되었습니다.
- Azure Active Directory 사용자 그룹을 기반으로 사용자 지정 검색 보고서를 만드는 기능 배포를 시작합니다. 예를 들어 마케팅 부서의 클라우드 사용을 확인하려면 사용자 그룹 가져오기 기능을 사용하여 마케팅 그룹을 가져온 다음, 이 그룹에 대한 사용자 지정 보고서를 만듭니다.

**기타 업데이트:**

- 이제 Cloud App Security에는 Office 365 감사 로그에서 지원되는 Microsoft Power BI 활동이 포함됩니다. 이 기능은 점진적으로 출시될 예정입니다. [Power BI 포털에서 이 기능](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/)을 사용하도록 설정해야 합니다.
- 활동 정책에서 모든 연결된 앱에서 사용자에 대해 수행되는 작업을 알리고 일시 중단할 수 있습니다. 예를 들어 사용자가 연결된 앱에 실패한 로그인이 여러 번 있을 때마다 항상 사용자의 관리자에게 알리고 즉시 사용자를 일시 중단하도록 정책을 설정할 수 있습니다.
 
### <a name="oob-release"></a>OOB 릴리스

- 전 세계를 휩쓰는 랜섬웨어에 대한 신속한 대응으로, 일요일에 Cloud App Security 팀은 WannaCrypt의 서명 확장이 포함된 새로운 [잠재적인 랜섬웨어 활동 검색 정책](use-case-ransomware.md) 템플릿을 포털에 추가했습니다. 지금 이 정책을 설정하는 것이 좋습니다.

### <a name="cloud-app-security-release-96"></a>Cloud App Security 릴리스 96

릴리스 날짜: 2017년 5월 8일

**새로운 기능:**

- Cloud App Security 콘솔 내부에서 관리자에게 부여할 권한을 관리할 수 있는 보안 독자 권한을 점진적으로 계속 공개합니다. 기본적으로 모든 Azure Active Directory, Office 365 글로벌 관리자 및 보안 관리자는 포털에서 모든 권한을 가집니다. Azure Active Directory 및 Office 365의 모든 보안 readers는 Cloud App Security에서 읽기 전용 액세스 권한을 가집니다. 자세한 내용은 [관리자 권한 관리](manage-admins.md)를 참조하세요.
- CSV 기반 로그용 사용자 정의 로그 파서에 대한 Cloud Discovery 지원이 완전히 공개되었습니다. Cloud App Security를 사용하면 특정 데이터에 어떤 열이 상호 연결되는지 설명하는 도구를 제공하여 이전에 지원되지 않는 어플라이언스에 대한 파서를 구성할 수 있습니다. 자세한 내용은 [사용자 지정 로그 파서](custom-log-parser.md)를 참조하세요.

**향상된 기능**

- 이제 Cloud Discovery가 Juniper SSG 어플라이언스를 지원합니다.
- 더 알아보기 쉽도록 Cisco ASA 로그에 대한 Cloud Discovery 지원이 향상되었습니다.
- 이제 대량 작업을 더 쉽게 실행하고 Cloud App Security 포털 표에서 여러 레코드를 선택할 수 있습니다. 대량 작업을 개선하기 위해 페이지 길이가 증가했습니다.
- 이제 Salesforce 데이터에 대한 **도메인별 아웃바운드 공유** 및 **공유 파일의 소유자** 기본 제공 보고서를 실행할 수 있습니다.
- 활동 데이터에서 추출된 관심 정보를 추적할 수 있는 추가 Salesforce 활동의 공개를 시작하고 있습니다. 여기에는 계정, 잠재 고객, 기회 및 다양한 기타 관심 Salesforce 개체를 보고 편집하는 작업이 포함됩니다.
- Exchange를 통해 사용자 사서함 또는 사서함 폴더에 어떤 권한이 부여되었는지 모니터링할 수 있는 새로운 활동이 추가되었습니다. 다음 활동이 포함됩니다.
  - 받는 사람 권한 추가
  - 받는 사람 권한 제거
  - 사서함 폴더 권한 추가
  - 사서함 폴더 권한 제거
  - 사서함 폴더 권한 설정

   예를 들어 다른 사용자의 사서함에 대한 **SendAs** 권한이 부여된 사용자를 모니터링할 수 있고, 이에 따라 이름으로 메일을 보낼 수 있습니다.


### <a name="cloud-app-security-release-95"></a>Cloud App Security 릴리스 95

릴리스 날짜: 2017년 4월 24일

**업데이트:**

- **계정** 페이지는 위험을 더 쉽게 검색할 수 있는 향상된 기능으로 업데이트되었습니다. 이제 내부 및 외부 계정을 더 쉽게 필터링할 수 있습니다. 사용자에게 관리자 권한이 있는지 여부를 한 눈에 확인합니다. 사용 권한 제거, 사용자 공동 작업 제거, 사용자 일시 중단과 같은 앱별 각 계정에 대한 작업을 수행할 수 있습니다. 또한 각 계정에 대해 가져온 [사용자 그룹](user-groups.md)이 표시됩니다. 

- Microsoft 회사 계정(Office 365 및 Azure Active Directory)의 경우 Cloud App Security가 프록시 주소, 별칭, SID 등과 같은 여러 사용자 ID를 단일 계정 아래에 그룹화합니다. 계정과 관련된 모든 별칭이 기본 메일 주소 아래에 표시됩니다. 사용자 ID 목록에 따라, 행위자가 사용자 ID인 작업의 경우 행위자가 기본 사용자 이름 UPN(사용자 계정 이름)으로 표시됩니다. UPN에 따라 그룹이 할당되고 정책이 적용됩니다. 이 변경으로 인해 예외 사항 및 그룹 기반 정책에 대해 활동에 대한 조사가 향상되고 모든 관련 활동이 동일한 세션으로 융합됩니다. 이 기능은 다음 달에 점진적으로 출시될 예정입니다.

- 브라우저 사용 기본 제공 보고서에 가능한 위험 요소로 로봇 태그가 추가되었습니다. 이제 브라우저 사용이 오래된 항목으로 태그가 지정되는 것 외에도 로봇이 브라우저 사용을 수행한 시기를 확인할 수 있습니다. 
- 콘텐츠 검사 파일 정책을 만들 때 이제 50개 이상의 일치 항목이 있는 파일만 포함하도록 필터를 설정할 수 있습니다.

### <a name="cloud-app-security-release-94"></a>Cloud App Security 릴리스 94

릴리스 날짜: 2017년 4월 2일

**새로운 기능:**

- Cloud App Security는 이제 Azure RMS와 통합되었습니다. Cloud App Security 포털에서 직접 Microsoft Rights Management를 통해 Office 365 OneDrive 및 Sharepoint Online의 파일을 보호할 수 있습니다. **파일** 페이지에서 보호를 수행할 수 있습니다. 자세한 내용은 [Azure Information Protection과 통합](azip-integration.md)을 참조하세요. 추가 애플리케이션에 대한 지원은 향후 버전에서 사용할 수 있습니다.
- 지금까지는 로봇 및 크롤러 작업이 네트워크에서 수행될 때 네트워크상의 사용자가 작업을 수행하지 않았기 때문에 특히 식별하기가 어려웠습니다. 사용자도 모르게 봇 및 크롤러가 컴퓨터에서 악성 도구를 실행할 수 있습니다. 이제, 로봇 및 크롤러가 네트워크에서 작업을 수행할 때 Cloud App Security가 이를 표시하는 도구를 제공합니다. 새 사용자 에이전트 태그를 사용하여 활동 로그에 있는 작업을 필터링할 수 있습니다. 사용자 에이전트 태그를 통해 로봇에서 수행한 모든 작업을 필터링할 수 있으며, 이러한 유형의 작업이 감지될 때마다 경고를 생성하는 정책을 만드는 데 사용자 에이전트 태그를 사용할 수 있습니다. 변칙 검색 경고에 포함되는 이 위험 작업이 향후 릴리스에 포함될 때 업데이트됩니다. 
- 새로운 통합 앱 권한 페이지를 통해 사용자가 타사 앱에 부여한 권한을 더욱 쉽게 조사할 수 있습니다. **조사** > **앱 사용 권한**을 클릭하면 이제 사용자가 타사 앱에 제공한 모든 사용 권한 목록을 볼 수 있습니다. 연결된 앱별 앱 사용 권한 페이지를 통해 다양한 앱과 부여된 사용 권한을 더 잘 비교할 수 있습니다. 자세한 내용은 [앱 사용 권한 관리](manage-app-permissions.md)를 참조하세요.
- 더욱 쉽게 조사할 수 있도록 테이블 서랍에서 바로 데이터를 필터링할 수 있습니다.
이제 조사 프로세스에서 훨씬 더 쉽게 피벗할 수 있는 새로운 상황별 작업을 통해 **활동 로그**의 **파일** 테이블 및 **앱 사용 권한** 페이지 기능이 향상되었습니다. 또한 구성 페이지에 대한 빠른 링크 및 한 번의 클릭을 통해 데이터를 복사하는 기능도 추가되었습니다. 자세한 내용은 [파일 및 활동 서랍 작업](file-filters.md)에 대한 정보를 참조하세요.
- Office 365 활동 로그 및 경고 롤아웃에 대한 Microsoft Teams 지원이 완료되었습니다.

### <a name="cloud-app-security-release-93"></a>Cloud App Security 릴리스 93

릴리스 날짜: 2017년 3월 20일

**새로운 기능:**

- 이제 가져온 사용자 그룹을 포함 또는 제외하는 정책을 적용할 수 있습니다. 
- 이제 Cloud App Security 익명화를 사용하여 사용자 지정 암호화 키를 구성할 수 있습니다. 자세한 내용은 [Cloud Discovery 익명화](cloud-discovery-anonymizer.md)를 참조하세요.
- 사용자 및 계정 관리를 보다 효율적으로 제어하기 위해 이제 **계정** 페이지 내에서 각 사용자 및 계정에 대한 Azure AD 계정 설정에 직접 액세스할 수 있습니다. 각 사용자 옆의 코그를 클릭하기만 하면 됩니다. 이 변경을 통해 고급 사용자 관리 기능 그룹 관리, MFA 구성, 사용자 로그인에 대한 세부 정보 및 로그인을 차단할 수 있는 기능에 쉽게 액세스할 수 있습니다. 
- 이제 Cloud App Security API를 통해 비사용 권한 앱에 대한 차단 스크립트를 내보낼 수 있습니다. 메뉴 모음에서 물음표를 클릭하고 다음 **API 설명서**를 클릭하여 Cloud App Security 포털의 API에 대해 알아봅니다.
- ServiceNow에 대한 Cloud App Security 앱 커넥터가 제네바, 헬싱키, 이스탄불에서 도입된 OAuth 토큰도 지원하도록 확장되었습니다. 이 변경을 통해 배포하는 사용자에 따라 달라지지 않는 ServiceNow에 더 강력한 API 연결을 제공합니다. 자세한 내용은 [Microsoft Cloud App Security에 ServiceNow 연결](connect-servicenow-to-microsoft-cloud-app-security.md)을 참조하세요. 기존 고객은 ServiceNow 앱 커넥터 페이지에서 설정을 업데이트할 수 있습니다.
- 타사 DLP 스캐너를 추가로 구성한 경우 이제 DLP 검색 상태에 각 커넥터 상태가 개별적으로 표시되므로 더 쉽게 확인할 수 있습니다.
- 이제 Cloud App Security에서 Office 365 감사 로그에서 지원되는 Microsoft 팀 활동도 지원합니다. 이 기능은 점진적으로 출시될 예정입니다.
- Exchange Online 가장 이벤트의 경우 이제 사용된 권한 수준 즉, 위임, 관리자 또는 위임된 관리자별로 필터링할 수 있습니다. **활동 개체** > **항목**을 검색하여 **활동 로그**에서 관심 있는 가장 수준을 표시하는 이벤트를 검색할 수 있습니다.
- Office 365 앱의 **앱 사용 권한** 탭의 앱 서랍에서 이제 각 앱의 **게시자**를 볼 수 있습니다. 또한 게시자를 필터로 사용하여 동일한 게시자의 앱을 추가로 확인할 수도 있습니다.
- 이제 위험한 IP 주소가 일반 **위치** 위험 요소 아래에서 가중 위험 요소가 아닌 독립 위험 요소로 표시됩니다. 
- 파일에 대해 Azure Information Protection 레이블을 사용하지 않도록 설정하면 사용하지 않도록 설정한 레이블이 Cloud App Security에서 사용 안 함으로 표시됩니다. 삭제된 레이블은 표시되지 않습니다.
 
**추가 Salesforce 지원:**

- 이제 Cloud App Security에서 Salesforce 사용자를 일시 중단 및 일시 중단 해제할 수 있습니다. 이 작업은 Salesforce 커넥터의 **계정** 탭에서 수행할 수 있습니다. 특정 사용자의 행 끝에 있는 코그를 클릭하고 **일시 중단** 또는 **일시 중단 해제**를 선택합니다. 일시 중단 및 일시 중단 해제는 정책의 일환으로 거버넌스 작업으로도 적용될 수 있습니다. Cloud App Security에서 수행하는 일시 중단 및 일시 중단 해제 활동은 모두 [거버넌스 로그](governance-actions.md)에 기록됩니다. 
- Salesforce 콘텐츠 공유에 대한 가시성 향상: 이제 공개적으로 공유한 파일, 그룹과 공유한 파일, 전체 Salesforce 도메인과 공유한 파일 등을 비롯해 어떤 파일을 누구와 공유했는지 확인할 수 있습니다. 향상된 가시성은 현재 연결된 Salesforce 앱과 새 Salesforce 앱에 소급해서 출시되며, 이 정보가 처음으로 업데이트되는 데 어느 정도 시간이 걸릴 수 있습니다.
- 다음 Salesforce 이벤트의 적용 범위를 개선했으며 **사용자 관리** 활동과 구분했습니다. 
  - 사용 권한 편집
  - 사용자 만들기
  - 역할 변경
  - 암호 다시 설정

### <a name="cloud-app-security-release-90-91-92"></a>Cloud App Security 릴리스 90, 91, 92

2017년 2월 출시됨

**특별 알림:**

이제 Cloud App Security는 ISO, HIPAA, CSA STAR, EU 모델 조항 등에 대한 Microsoft 규정 준수로 공식 인증되었습니다. [Microsoft 규정 준수 제안](https://www.microsoft.com/trustcenter/compliance/complianceofferings) 문서에서 Cloud App Security를 선택하여 전체 인증 목록을 확인합니다.

**새로운 기능:**

- **사용자 그룹 가져오기(미리 보기)** API 커넥터를 사용하여 앱을 연결할 때 이제 Cloud App Security를 사용하면 Office 365 및 Azure Active Directory에서 사용자 그룹을 가져올 수 있습니다. 가져온 사용자 그룹은 일반적으로 HR 직원이 보는 문서 조사, 임원 그룹에서 비정상적인 문제가 발생했는지 여부 확인 또는 관리자 그룹의 멤버가 미국 외부에서 활동을 수행했는지 확인 등의 시나리오에서 활용할 수 있습니다. 세부 정보 및 지침은 [사용자 그룹 가져오기를](user-groups.md) 참조하세요.

- 이제 활동 로그에서 사용자 및 그룹의 사용자를 필터링하여 특정 사용자가 수행한 활동 및 특정 사용자에 대해 수행된 활동을 표시할 수 있습니다. 예를 들어 사용자가 다른 사용자를 가장한 활동 및 다른 사용자가 이 사용자를 가장한 활동을 조사할 수 있습니다. 자세한 내용은 [활동](activity-filters.md)을 참조하세요.

- **파일** 페이지에서 파일을 조사할 때 특정 파일의 **협력자**로 드릴다운하면 이제 협력자에 대한 자세한 정보를 볼 수 있습니다. 이 정보에는 내부 또는 외부, 작성자 또는 Readers(파일 사용 권한)가 포함되며 파일을 그룹과 공유하면 그룹의 구성원인 모든 사용자를 볼 수 있습니다. 모든 사용자를 보면 그룹 멤버가 외부 사용자인지 알 수 있습니다.

- 이제 모든 어플라이언스에서 IPv6 지원이 제공됩니다.

- 이제 Cloud Discovery에서 Barracuda 어플라이언스를 지원합니다.

- 이제 Cloud App Security 시스템 알림에서 SIEM 연결 오류를 포함합니다. 자세한 내용은 [SIEM 통합](siem.md)을 참조하세요.

- 이제 Cloud App Security에서 다음 활동을 지원합니다.

  - **Office 365, SharePoint/OneDrive**: 애플리케이션 구성 업데이트, 그룹에서 소유자 제거, 사이트 삭제, 폴더 만들기

  - **Dropbox**: 그룹에 멤버 추가, 그룹에서 멤버 제거, 그룹 만들기, 그룹 이름 바꾸기, 팀 멤버 이름 변경

  - **Box**: 그룹에서 항목 제거, 항목 공유 업데이트, 그룹에 사용자 추가, 그룹에서 사용자 제거

### <a name="cloud-app-security-release-89"></a>Cloud App Security 릴리스 89

2017년 1월 22일 출시

**새로운 기능:**

- Cloud App Security에서 Office 365 보안 및 규정 준수 센터 DLP 이벤트를 보는 기능을 배포하기 시작했습니다. Office 365 보안 및 규정 준수 센터에서 DLP 정책을 구성한 경우 정책 일치가 검색되면 Cloud App Security 활동 로그에 해당 정책이 표시됩니다. 활동 로그의 정보에는 일치를 트리거한 파일 또는 메일이나 일치한 정책 또는 경고가 포함됩니다. **보안 이벤트** 활동을 사용하면 Cloud App Security 활동 로그에서 Office 365 DLP 정책 일치를 볼 수 있습니다. 이 기능을 사용하여 다음과 같이 할 수 있습니다.
  - Office 365 DLP 엔진에서 들어오는 모든 DLP 일치를 확인합니다.
  - 특정 파일, SharePoint 사이트 또는 정책에 대한 Office 365 DLP 정책 일치에 대해 경고합니다.
  - 더 폭넓은 컨텍스트(예: DLP 정책 일치를 트리거한 파일을 액세스하거나 다운로드한 외부 사용자)로 DLP 일치를 조사합니다.

- 활동 설명의 명확성과 일관성이 향상되었습니다. 이제 각 활동에 피드백 단추가 제공됩니다. 일부의 사항을 이해하지 못하거나 질문이 있다면 알려주세요.
 
**향상된 기능**

- 파일의 모든 외부 사용자를 제거할 수 있는, Office 365에 대한 새로운 거버넌스 작업이 추가되었습니다. 예를 들어 이 작업을 통해 **내부 전용 분류가 있는 파일에서 외부 공유를 제거**하는 정책을 구현할 수 있습니다.
- SharePoint Online에서 외부 사용자 식별이 향상되었습니다. “외부 사용자” 그룹을 필터링할 때 app@"sharepoint" 시스템 계정이 표시되지 않습니다.


### <a name="cloud-app-security-release-88"></a>Cloud App Security 릴리스 88

2017년 1월 8일 출시
 
**새로운 기능:**

- SIEM을 Cloud App Security에 연결. 이제 SIEM 에이전트를 구성하여 원하는 SIEM으로 경고 및 활동을 자동으로 보낼 수 있습니다. 현재 공개 미리 보기로 제공됩니다.  전체 설명서 및 자세한 내용은 SIEM과 통합을 살펴보세요.
- 이제 Cloud Discovery는 IPv6을 지원합니다. Palo Alto 및 Juniper에 대한 지원을 배포했으며, 이후 릴리스에서 더 많은 어플라이언스가 배포될 예정입니다.
 
**향상된 기능**

- 클라우드 앱 카탈로그에 새로운 위험 요소가 있습니다. 이제 앱이 사용자 인증을 필요로 하는지에 따라 앱의 등급을 지정할 수 있습니다. 인증을 적용하는 앱과 익명 사용을 허용하지 않는 앱은 안정성이 좀 더 높은 위험 점수를 받게 됩니다.
- 더 유용하고 일관되도록 새로운 활동 설명을 배포합니다. 활동 검색은 이 변경 내용의 영향을 받지 않습니다.
- 향상된 사용자 디바이스 식별을 포함해 Cloud App Security에서 디바이스 정보로 더 많은 수의 이벤트를 강화하도록 했습니다.

## <a name="updates-made-in-2016"></a>2016년의 업데이트
 
### <a name="cloud-app-security-release-87"></a>Cloud App Security 릴리스 87

2016년 12월 25일 출시

**새로운 기능:**

- 사용자 개인 정보를 보호하는 한편 Cloud Discovery를 사용할 수 있도록 [데이터 익명화](cloud-discovery-anonymizer.md)를 구현하는 중입니다. 데이터 익명화는 사용자 이름 정보를 암호화하여 수행됩니다.
- Cloud App Security에서 추가 어플라이언스로 차단 스크립트를 내보내는 기능을 구현하는 중입니다. 스크립트를 사용하면 미승인 앱에 대한 트래픽을 차단하여 섀도 IT를 손쉽게 줄일 수 있습니다. 이제 이 옵션을 다음에 사용할 수 있습니다. 
  - BlueCoat ProxySG
  - Cisco ASA
  - Fortinet
  - Juniper SRX
  - Palo Alto
  - Websense
- 파일 또는 폴더에 대해 설정된 고유한 권한을 삭제하여 파일에서 강제로 부모로부터 권한을 상속할 수 있는 새로운 파일 거버넌스 작업이 추가되었습니다. 이 파일 거버넌스 작업을 사용하면 부모 폴더로부터 상속하도록 파일 또는 폴더의 권한을 변경할 수 있습니다. 
- '외부'라고 하는 새로운 사용자 그룹이 추가되었습니다. 이 그룹은 내부 도메인에 속하지 않은 모든 사용자를 포함하기 위해 Cloud App Security에 의해 미리 구성된 기본 사용자 그룹입니다. 이 사용자 그룹을 필터로 사용할 수 있습니다. 예를 들면 외부 사용자가 수행한 활동을 찾을 수 있습니다.
- 이제 Cloud Discovery 기능은 Sophos Cyberoam 어플라이언스를 지원합니다.
 
**버그 수정:**

- SharePoint Online 및 비즈니스용 OneDrive 파일이 파일 정책 보고서 및 파일 페이지에 비공개 대신 내부로 표시되었습니다. 이 버그가 수정되었습니다.

### <a name="cloud-app-security-release-86"></a>Cloud App Security 릴리스 86

2016년 12월 13일 출시

**새로운 기능:**

- 모든 Cloud App Security 독립형 라이선스는 일반 설정으로(정책을 만들지 않고) Azure Information Protection 검사를 수행할 수 있는 기능을 제공합니다. 
 
**향상된 기능**

- 이제 파일 이름용 파일 필터와 파일 및 정책용 MIME 형식 필터에 "or"를 사용할 수 있습니다. 이 변경을 통해 개인 데이터에 대한 정책을 만들 때 "passport" 또는 "driver"라는 단어 입력과 같은 시나리오를 사용할 수 있습니다. 필터는 파일 이름에 "passport" 또는 "driver"가 있는 모든 파일과 일치합니다.
- 기본적으로 DLP 콘텐츠 검사 정책을 실행하면 위반 결과의 데이터가 마스킹됩니다. 이제 위반 항목의 마지막 네 문자를 마스크 해제할 수 있습니다. 

**사소하게 향상된 기능:**

- 규칙 전달, 대리자 사서함 권한의 추가 및 제거와 관련된 새로운 Office 365(Exchange) 사서함 관련 이벤트.
- Azure Active Directory에서 새 앱에 대한 승인 허용을 감사하는 새 이벤트. 

### <a name="cloud-app-security-release-85"></a>Cloud App Security 릴리스 85

2016년 11월 27일 출시

**새로운 기능:**

- 승인된 앱과 연결된 앱을 구분했습니다. 승인 및 미승인은 이제 검색된 앱과 앱 카탈로그의 모든 앱에 적용할 수 있는 태그입니다. 연결된 앱은 가시성과 제어력을 높이기 위해 API 커넥터를 사용하여 연결한 앱입니다. 이제 앱에 승인 또는 미승인으로 태그 지정하거나 사용 가능한 경우 앱 커넥터를 사용하여 앱을 연결할 수 있습니다. 
- 이 변경의 일부로 승인 앱 페이지가 커넥터에 대한 상태 데이터를 표시하는 새로 디자인된 **연결된 앱** 페이지로 바뀌었습니다. 
- 로그 수집기는 **원본** 아래의 **설정** 메뉴에서 별도의 줄로 더 쉽게 액세스할 수 있습니다. 
- 활동 정책 필터를 만들 때 동일한 사용자가 동일한 대상 개체에 대해 수행하는 경우 반복되는 활동을 무시하도록 선택하여 가양성을 줄일 수 있습니다. 예를 들어 동일한 사람이 동일한 파일을 여러 번 다운로드하려고 해도 경고가 트리거되지 않습니다. 
- 활동 서랍이 향상되었습니다. 이제 활동 서랍에서 활동 개체를 클릭할 때 드릴다운하여 자세한 정보를 확인할 수 있습니다.

**향상된 기능**

- 비정상 감지 엔진이 개선되었습니다. 예를 들어 불가능한 이동 경고의 경우 이제 IP 정보가 경고 설명에 제공됩니다.
- 복잡한 필터가 개선되어 동일한 필터를 두 번 이상 추가하여 필터링된 결과를 미세 조정할 수 있습니다. 
- Dropbox에서 파일 및 폴더 작업이 분리되어 더 알아보기 쉬워졌습니다. 
  
**버그 수정:**

- 가양성을 생성하던 시스템 경고 메커니즘의 버그가 수정되었습니다.

### <a name="cloud-app-security-release-84"></a>Cloud App Security 릴리스 84

2016 년 11 월 13 일 출시

**새로운 기능:**

- 이제 Cloud App Security에서는 향상된 통합 및 자동 프로비저닝이 포함된 Microsoft Azure Information Protection을 지원합니다. 태그 보안 분류를 사용하여 파일을 필터링하고 파일 정책을 설정한 다음 보려는 분류 레이블을 설정할 수 있습니다. 또한 레이블은 분류가 조직의 사용자에 의해 설정되었는지 다른 테넌트의 사용자(외부)에 의해 설정되었는지를 나타냅니다. Azure Information Protection 분류 레이블을 기반으로 활동 정책을 설정하고 Office 365에서 분류 레이블의 자동 검색을 사용하도록 설정할 수도 있습니다. 이 훌륭한 새 기능을 활용하는 방법에 관한 자세한 내용은 [Azure Information Protection와의 통합](azip-integration.md)을 참조하세요.
 
**향상된 기능**

- Cloud App Security 활동 로그가 다음과 같이 향상되었습니다. 
  - 보안 및 규정 준수 센터의 Office 365 이벤트가 이제 Cloud App Security와 통합되어 **활동 로그**에 표시됩니다.
  - 모든 Cloud App Security 활동은 Cloud App Security 활동 로그에 관리자 활동으로 등록됩니다.
- 파일 관련 경고의 조사를 돕기 위해, 파일 정책에서 발생하는 각 경고에서 이제 해당 파일에서 수행한 활동의 목록을 볼 수 있습니다.
- 비정상 검색 엔진의 이동 불가능 알고리즘이 작은 테넌트를 더 잘 지원하도록 개선되었습니다. 
 
**사소하게 향상된 기능:**

- **활동 내보내기 제한**이 10,000개로 올라갔습니다. 
- 클라우드 검색 수동 업로드 프로세스에서 **스냅숏 보고서**를 만들 때 이제 로그 처리에 걸리는 예상 시간이 더 정확하게 표시됩니다. 
- 파일 정책에서 **공동 작업자 제거** 거버넌스 작업이 이제 그룹에도 적용됩니다.
- **응용 프로그램 권한** 페이지에서도 여러 기능이 사소하게 향상되었습니다. 
- Office 365에 연결하는 응용 프로그램에 대해 권한이 부여된 사용자가 10,000명을 넘을 경우, 이전에는 목록이 느리게 로드되었습니다. 이 속도 저하가 수정되었습니다.
- **응용 프로그램 카탈로그**에 지불 카드 업계와 관련된 특성이 더 추가되었습니다.


### <a name="cloud-app-security-release-83"></a>Cloud App Security 릴리스 83

릴리스 날짜: 2016년 10월 30일

**새로운 기능:**

- [활동 로그](activity-filters.md)와 [파일 로그](file-filters.md)에서 필터링을 간소화하기 위해 유사한 필터를 통합했습니다. 활동 필터 사용: 활동 개체, IP 주소 및 사용자 파일 필터 공동 작업자를 사용하여 원하는 것을 정확하게 찾습니다.
- 활동 로그 서랍의 **소스**에서 **원시 데이터 보기**에 대한 링크를 클릭할 수 있습니다. 이 작업은 앱 이벤트에 더 많은 드릴다운을 위해 활동 로그를 생성하는 데 사용되는 원시 데이터를 다운로드합니다. 
- Okta의 추가 로그인 활동에 대한 지원이 추가되었습니다. [비공개 미리 보기]
- Salesforce의 추가 로그인 활동에 대 한 지원이 추가되었습니다. 

**향상된 기능**

- Cloud Discovery 스냅숏 보고서 및 문제 해결의 사용 편의성이 향상되었습니다.
- 여러 응용 프로그램에서 경고 목록의 가시성이 향상되었습니다.
- 새 Cloud Discovery 연속 보고서를 만들 때의 사용 편의성이 향상되었습니다.
- 거버넌스 로그의 사용 편의성이 향상되었습니다.

### <a name="cloud-app-security-release-82"></a>Cloud App Security 릴리스 82

릴리스 날짜: 2016년 10월 9일

**향상된 기능**

- 이제 **메일 변경** 및 **암호 변경** 활동이 Salesforce에서 일반 **사용자 관리** 활동과 독립적입니다.
- SMS 일일 경고 제한에 대한 설명이 추가되었습니다. 매일(UTC) 전화 번호당 최대 10개의 메시지가 전송됩니다.
- Safe Harbor를 대체한 개인 정보 보호와 관련하여 새 인증서가 Cloud Discovery 특성에 추가되었습니다(미국 공급업체와만 관련됨).
- API 커넥터 오류 메시지에 대한 문제 해결이 추가되어 문제를 더 쉽게 수정할 수 있습니다.
- Office 365 타사 앱 검색의 업데이트 빈도가 개선되었습니다.
- Cloud Discovery 대시보드의 기능이 개선되었습니다.
- 검사점 Syslog 파서가 개선되었습니다.
- 타사 앱 금지 및 금지 취소에 대한 거버넌스 로그가 개선되었습니다.
 
**버그 수정:**
 
- 로고를 업로드하는 프로세스가 개선되었습니다.
 
### <a name="cloud-app-security-release-81"></a>Cloud App Security 릴리스 81

릴리스 날짜: 2016년 9월 18일

**향상된 기능**

- 이제 Cloud App Security는 Office 365의 자사 앱입니다. 이제부터 단 한 번의 클릭으로 Office 365를 Cloud App Security에 연결할 수 있습니다.

- 거버넌스 로그의 새로운 모양 - 이제 활동 로그 및 파일 테이블과 동일하게 명확하고 유용한 모양으로 업그레이드되었습니다. 새 필터를 사용하여 필요한 항목을 쉽게 찾고 거버넌스 작업을 모니터링할 수 있습니다. 
- 여러 번의 로그인 실패 및 추가 위험 요소에 대한 변칙 검색 엔진의 기능이 개선되었습니다.
- Cloud Discovery 스냅숏 보고서가 개선되었습니다.
- 활동 로그의 관리 활동이 개선되었습니다. 암호 변경, 사용자 업데이트, 암호 재설정이 이제 활동이 관리 활동으로 수행되었는지 여부를 나타냅니다.
- 시스템 경고에 대한 경고 필터가 개선되었습니다. 
- 경고 내의 정책에 대한 레이블이 정책 보고서로 다시 연결됩니다.
- Dropbox 파일에 지정된 소유자가 없는 경우 알림 이메일 메시지가 설정한 받는 사람에게 전송됩니다. 
- Cloud App Security에서 24개 언어를 추가로 지원하여 지원이 총 41개 언어로 확장됩니다.  


### <a name="cloud-app-security-release-80"></a>Cloud App Security 릴리스 80

릴리스 날짜: 2016년 9월 4일 

**향상된 기능**

- DLP 검색이 실패할 경우 Cloud App Security에서 파일을 검색할 수 없는 이유에 대한 설명이 제공됩니다. 자세한 내용은 [콘텐츠 검사](https://aka.ms/aka.ms/cas-contentinspection)를 참조하세요.
- 이동 불가능 경고의 개선을 포함하여 변칙 검색 엔진의 기능이 향상되었습니다.
- 경고 해제 환경이 개선되었습니다. Cloud App Security 팀에서 경고가 흥미로운지 여부와 그 이유를 알 수 있도록 피드백을 추가할 수도 있습니다. 피드백은 Cloud App Security 검색 기능을 개선하는 데 사용됩니다.
- Cisco ASA Cloud Discovery 파서가 개선되었습니다.
- 이제 Cloud Discovery 로그 수동 업로드가 완료되면 메일 알림을 받습니다.

### <a name="cloud-app-security-release-79"></a>Cloud App Security 릴리스 79

릴리스 날자: 2016년 8월 21일 

**새로운 기능:**

- **새로운 Cloud Discovery 대시보드** - 조직에서 클라우드 앱이 어떻게 사용되는지를 효과적으로 파악할 수 있도록 설계된 완전히 새로운 Cloud Discovery 대시보드를 사용할 수 있습니다. 이 대시보드에서는 사용되고 있는 앱의 종류, 미해결 경고 및 조직에서 앱의 위험 수준을 한눈에 파악할 수 있습니다. 또한 조직 최고의 앱 사용자를 확인할 수 있으며 앱 본사 위치 지도를 제공합니다. 새 대시보드는 가장 관심 있는 항목에 따라 데이터를 필터링할 수 있는 더 많은 옵션을 제공하여 특정 뷰를 생성할 수 있으며, 이해하기 쉬운 그래픽을 통해 한눈에 볼 수 있는 전체 사진을 제공합니다.

- **새 Cloud Discovery 보고서** - Cloud Discovery 결과를 보려면 이제 스냅숏 보고서와 연속 보고서라는 두 종류의 보고서를 생성할 수 있습니다. 스냅숏 보고서는 방화벽 및 프록시에서 수동으로 업로드하는 트래픽 로그 집합에 대해 임시 가시성을 제공합니다. 연속 보고서는 Cloud App Security의 로그 수집기를 사용하여 네트워크에서 전달되는 모든 로그의 결과를 보여 줍니다. 이러한 새 보고서는 모든 데이터에 대한 향상된 가시성, Cloud App Security 기계 학습 변칙 검색 엔진에 의해 식별된 비정상적인 사용의 자동 식별 및 강력하고 세부적인 정책 엔진을 사용하여 정의된 비정상적인 사용의 식별 기능을 제공합니다. 자세한 내용은 [Cloud Discovery 설정](set-up-cloud-discovery.md)을 참조하세요.
 
**향상된 기능**

- 다음 페이지에서 일반적인 사용 편의성이 향상되었습니다. 정책 페이지, 일반 설정, 이메일 설정
- 이제 경고 표에서 읽은 경고와 읽지 않은 경고를 더 쉽게 구분할 수 있습니다. 읽은 경고는 왼쪽에 파란색 줄이 있고 회색으로 표시되어 이미 읽었음을 나타냅니다.
- 활동 정책 **반복 활동** 매개 변수가 업데이트되었습니다. 
- 계정 페이지에서 사용자 **유형** 열이 추가되어 각 사용자의 사용자 계정 유형을 확인할 수 있습니다. 사용자 유형은 앱마다 다릅니다. 
- OneDrive 및 SharePoint의 파일 관련 작업에 대해 근 실시간 지원이 추가되었습니다. 파일이 변경되면 거의 즉시 Cloud App Security에서 검색을 트리거합니다.


### <a name="cloud-app-security-release-78"></a>Cloud App Security 릴리스 78

릴리스 날짜: 2016년 8월 7일

**향상된 기능**

- 특정 파일에서 마우스 오른쪽 단추를 클릭하면 **관련 항목 찾기**를 사용할 수 있습니다. 활동 로그에서 대상 개체 필터를 사용한 다음 특정 파일을 선택할 수 있습니다.

- Juniper 및 Cisco ASA가 추가되는 등 Cloud Discovery 로그 파일 파서가 개선되었습니다.
- 이제 Cloud App Security를 사용하면 경고를 해제할 때 향상된 경고에 대한 피드백을 제공할 수 있습니다. 경고를 해제하는 이유를 알려줌으로써 Cloud App Security 경고 기능의 품질을 향상시킬 수 있습니다. 예를 들어 관심이 없고, 너무 많은 유사한 경고를 받았고, 실제 심각도를 더 낮춰야 하며, 경고가 정확하지 않습니다.
- 파일 정책 보기에서나 파일을 볼 때 파일 창을 열면 일치 정책에 대한 새 링크가 추가되었습니다. 이 링크를 클릭하면 모든 일치 항목을 볼 수 있으며 이제 모든 항목을 해제할 수도 있습니다.
- 사용자가 속한 조직 구성 단위가 모든 관련 경고에 추가됩니다.
- 수동으로 업로드한 로그에 대한 처리가 완료되면 메일 알림이 전송되어 알려줍니다.


### <a name="cloud-app-security-release-77"></a>Cloud App Security 릴리스 77

릴리스 날짜: 2016년 7월 24일

**향상된 기능**

- Cloud Discovery 내보내기 단추 아이콘의 유용성이 향상되었습니다.
- 활동을 조사할 때 사용자 에이전트가 구문 분석되지 않은 경우 원시 데이터가 표시될 수 있습니다.
- 변칙 검색 엔진에 새로운 두 가지 위험 요소가 추가되었습니다. 
  - Cloud App Security에서 봇네트와 익명 IP 주소에 연결된 IP 주소 태그를 위험 계산의 일부로 사용합니다. 
  - Office 365 활동이 높은 다운로드 비율로 모니터링됩니다. Office 365 다운로드 비율이 조직 또는 특정 사용자의 일반 다운로드 비율보다 훨씬 더 높은 경우 변칙 검색 경고가 트리거됩니다. 
- 이제 Cloud App Security가 새 Dropbox [보안 공유 기능](https://blogs.dropbox.com/dropbox/2016/06/new-dropbox-productivity-tools/) API와 호환됩니다. 
- 다음을 포함하여 검색 로그 구문 분석 오류에 세부 정보를 추가하도록 향상되었습니다. 클라우드 관련 트랜잭션 없음, 모든 이벤트가 오래됨, 손상된 파일, 로그 형식이 일치하지 않음
- 활동 로그 날짜 필터가 개선되어 이제 시간별로 필터링하는 기능을 포함합니다.
- IP 주소 범위 페이지의 유용성이 향상되었습니다.
- 이제 Cloud App Security에 Microsoft Azure Information Protection(Preview 버전)에 대한 지원이 포함됩니다. 태그 보안 분류를 사용하여 파일을 필터링하고 파일 정책을 설정할 수 있습니다. 그런 다음, 보려는 분류 레이블의 수준을 설정합니다. 또한 레이블은 분류가 조직의 사용자에 의해 설정되었는지 다른 테넌트의 사용자(외부)에 의해 설정되었는지를 나타냅니다. 



### <a name="cloud-app-security-release-76"></a>Cloud App Security 릴리스 76

릴리스 날짜: 2016년 7월 10일

**향상된 기능**

- 이제 기본 제공 보고서의 사용자 목록을 내보낼 수 있습니다.
- 집계된 활동 정책의 유용성이 향상되었습니다.
- TMG W3C 방화벽 로그 메시지 파서에 대한 지원이 향상되었습니다.
- 파일 거버넌스 작업 드롭다운의 유용성이 향상되어, 이제 공동 작업, 보안 및 조사 작업으로 구분됩니다.
- 다음의 Exchange Online 활동에 대한 이동 불가능 검색 기능이 향상되었습니다. 이메일 보내기
- 새로운 제목(이동 경로) 목록이 경고 및 정책 페이지 맨 위에 추가되어 더 쉽게 탐색할 수 있습니다.

**버그 수정:**
- 파일 정책에 대한 DLP 설정에서 신용 카드에 대해 미리 설정된 식이 모두: 재무: 신용 카드로 변경되었습니다.


### <a name="cloud-app-security-release-75"></a>Cloud App Security 릴리스 75
릴리스 날짜: 2016년 6월 27일

**새로운 기능:**

- 지원되는 Salesforce 이벤트 목록에 새로운 추가 항목이 추가되었습니다.  이벤트에는 보고서, 공유 링크, 콘텐츠 배포, 가장된 로그인 등에 대한 인사이트 제공이 포함됩니다.
- Cloud App Security 대시보드의 연결된 앱 아이콘이 지난 30일을 반영하도록 대시보드에 표시된 앱의 상태에 맞게 정렬되었습니다.
- 전자 화면을 지원합니다.

**버그 수정:**

- 이제 SMS 경고 전화 번호의 유효성이 삽입 시 검사됩니다.

### <a name="cloud-app-security-release-74"></a>Cloud App Security 릴리스 74

릴리스 날짜: 2016년 6월 13일

- 경고 화면이 업데이트되어 한눈에 더 많은 정보를 제공하게 되었습니다. 업데이트에는 모든 사용자 활동을 한눈에 볼 수 있는 기능, 활동 맵, 관련 사용자 거버넌스 로그, 경고가 트리거된 이유에 대한 설명, 사용자 페이지의 추가 그래프와 지도가 포함됩니다. 
- 이제 Cloud App Security에서 생성된 이벤트에 이벤트 유형, 형식, 정책 그룹, 관련 개체 및 설명이 포함됩니다.
- Office 365 ProPlus, OneNote, Office Online 및 Exchange Online Protection에 대한 새 IP 주소 태그가 추가되었습니다.
- 이제 기본 검색 메뉴에서 로그를 업로드하는 옵션이 있습니다.
- IP 주소 범주 필터가 개선되었습니다. IP 주소 범주 null이 이제 분류되지 않음이라고 합니다. IP 주소 데이터가 없는 모든 활동을 포함하도록 값 없음이라는 새 범주가 추가되었습니다.
- 이제 Active Directory 보안 그룹과의 혼동을 피하기 위해 Cloud App Security의 보안 그룹을 사용자 그룹이라고 합니다.
- 이제 IP 주소별로 필터링하고 IP 주소가 없는 이벤트를 제외할 수 있습니다. 
- 활동 정책 및 파일 정책에서 일치 항목이 검색될 경우 전송되는 알림 메일에 대한 설정이 변경되었습니다. 이제 알림과 함께 참조로 지정할 받는 사람의 메일 주소를 추가할 수 있습니다.


### <a name="cloud-app-security-release-73"></a>Cloud App Security 릴리스 73

릴리스 날짜: 2016년 5월 29일

- 업데이트된 경고 기능: 이제 이메일을 통해 전송되거나 문자 메시지로 전송되도록 정책별 경고를 설정할 수 있습니다.
- 경고 페이지: 고급 해결 옵션 및 인시던트 관리가 가능하도록 디자인이 개선되었습니다.
- 정책 조정: 이제 경고를 통해 경고 해결 옵션에서 직접 정책 설정 페이지로 이동할 수 있어 경고를 기반으로 하여 더 쉽게 미세 조정할 수 있습니다.
- 고객 의견을 바탕으로 하여 변칙 검색 위험 점수 계산이 향상되고 가양성 비율이 감소했습니다.
- 이제 활동 로그 내보내기에 이벤트 ID, 이벤트 범주 및 이벤트 유형 이름이 포함됩니다.
- 정책 만들기 거버넌스 작업의 모양과 유용성이 개선되었습니다.
- Office 365의 조사 및 제어가 간소화됨: Office 365를 선택하면 Office 365 Suite에 속하는 모든 앱이 자동으로 선택됩니다.
- 이제 알림이 연결된 앱에 구성된 대로 메일 주소로 전송됩니다. 
- 연결 오류가 발생할 경우 이제 클라우드 앱에서 오류에 대한 자세한 설명을 제공합니다.
- 이제 파일이 정책과 일치하는 경우 파일에 액세스할 수 있는 URL이 파일 창에서 제공됩니다.
- 활동 정책 또는 변칙 검색 정책에 의해 경고가 트리거되면 이제 일치 항목에 대한 정보를 제공하는 새로운 자세한 알림이 전송됩니다. 
- 앱 커넥터 연결이 끊어지면 자동화된 시스템 경고가 트리거됩니다.
- 이제 경고 페이지 내에서 단일 경고 또는 선택한 대량 경고를 해제하고 해결할 수 있습니다.

### <a name="cloud-app-security-release-72"></a>Cloud App Security 릴리스 72

릴리스 날짜: 2016년 5월 15일

-  다음과 같이 일반적인 모양과 인프라가 개선되었습니다.

   - 클라우드 검색 수동 로그 업로드 프로세스에 대한 더 많은 지원을 제공하는 새로운 다이어그램이 마련되었습니다.
   - 인식할 수 없는("기타") 로그 파일을 업데이트하는 프로세스가 개선되었습니다. 이 프로세스에는 추가 검토가 필요한 파일임을 알리는 팝업이 포함되어 있습니다. 데이터를 사용할 수 있을 때 알림을 받게 됩니다.
   - 오래된 브라우저 및 운영 체제에 대한 활동 및 파일 로그를 조사하는 경우 더 많은 활동 및 파일 위반이 강조 표시됩니다.

- Cisco ASA, Cisco FWSM, Cisco Meraki, W3C가 추가되는 등 클라우드 검색 로그 파일 파서가 개선되었습니다.
- 클라우드 검색과 관련한 알려진 문제가 개선되었습니다.
- 소유자의 도메인 및 내부/외부 소속에 대한 새로운 활동 필터가 추가되었습니다.
- 모든 Office 365 개체(파일, 폴더, URL)를 검색할 수 있는 새로운 필터가 추가되었습니다.
- 변칙 검색 정책에 대한 최소 위험 점수를 구성하는 기능이 추가되었습니다.
- 정책을 위반할 경우 전송되도록 경고를 설정할 때, 이제 경고가 발생하도록 할 최소 심각도 수준을 설정할 수 있습니다. 이에 대한 조직의 기본 설정을 사용하도록 선택할 수 있으며, 조직에 대한 기본값으로 특정 경고 설정을 지정할 수 있습니다.

### <a name="next-steps"></a>다음 단계 

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
