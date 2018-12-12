---
title: Microsoft Cloud App Security 조건부 액세스 앱 제어로 보호| Microsoft Docs
description: 이 문서에서는 Cloud App Security 조건부 액세스 앱 제어 역방향 프록시의 작동 방식에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/9/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 35a43120-bf67-4cf9-9b48-ebe157dbbd18
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 620bcbc8751ac782c947b2a761e8250ddc0f5807
ms.sourcegitcommit: c497253a7ab63973bb806607e5f15dece91640be
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53124267"
---
# <a name="protect-apps-with-microsoft-cloud-app-security-conditional-access-app-control"></a>Microsoft Cloud App Security 조건부 액세스 앱 제어로 앱 보호

*적용 대상: Microsoft Cloud App Security*

>[!div class="step-by-step"]
[다음: 조건부 액세스 앱 제어 배포 »](proxy-deployment-aad.md)


오늘날의 작업 공간에서는 클라우드 환경에서 실제로 어떤 일이 일어나는지 파악하는 것만으로는 충분하지 않는 경우가 많습니다. 직원이 의도적으로 또는 실수로 데이터와 조직을 위험에 노출하기 전에 실시간으로 위반 및 누출을 방지하고자 합니다. 조직의 사용자가 클라우드 앱에서 제공하는 대부분의 서비스 및 도구를 최대한 활용하고 자신의 디바이스를 작동할 수 있도록 하는 것이 중요합니다. 동시에 데이터 누수 및 데이터 절도로부터 실시간으로 조직을 보호할 수 있는 도구가 필요합니다. Microsoft Cloud App Security는 Azure Active Directory와 함께 조건부 액세스 앱 제어를 사용하는 전체적이고 통합된 환경에서 이러한 기능을 제공합니다.

> [!NOTE]
> Cloud App Security 조건부 액세스 앱 제어를 사용하려면 [Azure Active Directory P1 라이선스](https://azure.microsoft.com/pricing/details/active-directory/) 및 활성 Microsoft Cloud App Security 구독이 필요합니다.
>

## <a name="how-it-works"></a>작동 방식

조건부 액세스 앱 제어는 역방향 프록시 아키텍처를 사용하며 Azure AD 조건부 액세스와 고유하게 통합됩니다. Azure AD 조건부 액세스를 사용하면 특정 조건에 따라 조직의 앱에 대한 액세스 제어를 적용할 수 있습니다. 조건은 *who*(사용자 또는 사용자 그룹)와 *what*(클라우드 앱) 및 *where*(위치 및 네트워크) 조건부 액세스 정책이 적용됩니다. 조건을 확인한 후 사용자를 액세스 및 세션 제어를 적용하여 조건부 액세스 앱 제어로 데이터를 보호할 수 있는 Microsoft Cloud App Security로 라우팅할 수 있습니다.

조건부 액세스 앱 제어를 통해 사용자는 액세스 및 세션 정책에 따라 실시간으로 앱 액세스 및 세션을 모니터링하고 제어할 수 있습니다. 액세스 및 세션 정책은 Cloud App Security 포털에서 사용되어 필터를 자세히 구체화하고 사용자에 대해 수행할 작업을 설정합니다. 액세스 및 세션 정책을 사용하면 다음을 수행할 수 있습니다.

- **다운로드 시 차단**: 중요한 문서의 다운로드를 차단할 수 있습니다. 예를 들어 관리되지 않는 장치에 다운로드하는 경우에는 차단됩니다.

- **다운로드 시 보호**: 중요한 문서의 다운로드를 차단하는 대신 다운로드 시 암호화를 통해 문서를 보호하도록 요구할 수 있습니다. 이 암호화는 데이터가 신뢰할 수 없는 디바이스에 다운로드되는 경우 문서가 보호되고 사용자 액세스가 인증되는지 확인합니다. 

- **낮은 신뢰 사용자 세션 모니터링**: 위험한 사용자가 앱에 로그인하고 해당 작업이 세션 내에서 기록될 때 모니터링됩니다. 사용자 동작을 조사하고 분석하여 나중에 세션 정책을 적용해야 하는 위치와 조건을 이해할 수 있습니다. 

- **액세스 차단**: 관리되지 않는 장치 또는 회사 네트워크가 아닌 곳의 사용자에 대해 특정 앱에 대한 액세스를 완전히 차단할 수 있습니다.

- **읽기 전용 모드 만들기**: 사용자 지정 앱 내 작업을 모니터링하고 차단하여 특정 사용자의 특정 앱에 대한 읽기 전용 모드를 만들 수 있습니다.  

- **비회사 네트워크의 사용자 세션 제한**: 회사 네트워크에 속하지 않은 위치에서 보호되는 앱에 액세스하는 사용자는 액세스가 제한됩니다. 중요한 자료의 다운로드가 차단되거나 보호됩니다.

### <a name="how-session-control-works"></a>세션 제어 작동 방식

조건부 액세스 앱 제어를 사용하여 세션 정책을 만들면 사용자를 앱이 아니라 역방향 프록시를 통해 리디렉션하여 사용자 세션을 제어할 수 있습니다. 이때부터 사용자 요청과 응답은 앱으로 직접 이동하는 것이 아니라 Microsoft Cloud App Security를 통해 이동합니다.

세션 내에서 사용자를 유지하기 위해 앱 세션 내에서 관련된 모든 URL, Java 스크립트 및 쿠키를 Microsoft Cloud App Security URL로 바꿉니다. 예를 들어 앱에서 도메인이 myapp.com으로 끝나는 링크가 포함된 페이지를 반환하는 경우 링크는 연결이 myapp.com.us.cas.ms와 같이 끝나는 도메인으로 바뀝니다. 

이 방법을 사용하면 디바이스에 아무 것도 설치할 필요가 없습니다. 이 방법은 관리되지 않는 디바이스에서 세션을 모니터링하는 경우에 가장 좋습니다. 

Microsoft Cloud App Security를 통해 세션이 전달된 후 다음 작업을 수행할 수 있습니다.

1. 사용자 활동에 대한 트래픽 검사
2. Microsoft Cloud App Security 활동 로그에 식별된 활동 표시
3. 트래픽 로그 저장 및 분석
4. 관리자가 트래픽 로그를 내보낼 수 있도록 설정
5. 세션에서 정책 적용

## <a name="managed-device-identification"></a>관리 장치 식별

조건부 액세스 앱 제어를 사용하면 장치를 관리할지 여부를 고려하는 정책을 만들 수 있습니다. 디바이스를 관리하는지 여부를 확인하기 위해 이 기능은 다음을 사용합니다.

- 준수 장치
- 도메인 가입 장치
- 클라이언트 인증서 배포
 
### <a name="compliant-and-domain-joined-devices"></a>준수 및 도메인 가입 장치

Azure AD 조건부 액세스를 사용하면 준수 및 도메인 가입 장치 정보를 Microsoft Cloud App Security에 직접 전달할 수 있습니다. 여기서 장치 상태를 필터로 사용하는 액세스 정책 또는 세션 정책을 개발할 수 있습니다.
자세한 내용은 [Azure Active Directory의 장치 관리 소개](https://docs.microsoft.com/azure/active-directory/device-management-introduction)를 참조하세요. 

### <a name="client-certificate-authenticated-devices"></a>클라이언트 인증서 인증 장치

장치 식별 메커니즘에서는 클라이언트 인증서를 사용하여 관련 장치에서 인증을 요청할 수 있습니다. 조직에 이미 배포된 기존 클라이언트 인증서를 사용하거나 관리 디바이스에 새 클라이언트 인증서를 배포할 수 있습니다. 그런 다음, 해당 인증서의 존재를 사용하여 액세스 및 세션 정책을 설정합니다. 클라이언트 인증서를 배포하는 방법에 대한 내용은 [Azure AD 앱용 조건부 액세스 앱 제어 배포](proxy-deployment-aad.md)를 참조하세요.
 
## <a name="supported-apps-and-clients"></a>지원되는 앱 및 클라이언트

조건부 액세스 앱 제어는 현재 [Azure AD 앱 프록시](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)로 구성된 온-프레미스 호스팅 웹앱과 함께 Single Sign-On으로 구성된 SAML 및 Open ID Connect 앱을 지원합니다.
> [!NOTE]
> 조건부 액세스 앱 제어는 Azure AD 이외의 ID 공급자로 구성된 앱도 지원합니다. 이 시나리오에 대한 자세한 내용은 mcaspreview@microsoft.com으로 이메일을 보내주세요.

세션 제어는 주요 플랫폼의 모든 브라우저에서 사용할 수 있습니다. 모바일 앱과 데스크톱 앱도 차단되거나 허용될 수 있습니다. 기본적으로 Azure AD와 통합하면 Azure AD에서 Single Sign-On을 통해 SAML 및 Open ID Connect 앱으로 구성된 모든 앱이 지원될 수 있습니다. 추천 앱은 다음과 같습니다.

- AWS
- 상자
- Concur
- CornerStone on Demand
- DocuSign
- Dropbox
- Egnyte
- G Suite
- GitHub
- HighQ
- JIRA/Confluence
- Salesforce
- ServiceNow
- Slack
- Tableau
- Workday
- Workiva
- Workplace by Facebook
- Exchange Online(미리 보기)
- 비즈니스용 OneDrive(미리 보기)
- Power BI(미리 보기)
- SharePoint Online(미리 보기)
- Azure DevOps(Visual Studio Team Services)(미리 보기)
- Yammer(미리 보기)



세션 제어에 추가 앱이 계속 등록되고 있습니다. 여기에서 언급되지 않은 특정 앱에 관심이 있다면 [앱에 대한 정보를 보내주세요](mailto:casfeedback@microsoft.com). 온보딩에 대해 관심 있는 사용 사례를 보내주세요.



>[!div class="step-by-step"]
[다음: 조건부 액세스 앱 제어 배포 »](proxy-deployment-aad.md)


## <a name="next-steps"></a>다음 단계
[Azure AD 앱용 조건부 액세스 앱 제어 배포](proxy-deployment-aad.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  


