---
title: "Microsoft Cloud App Security 프록시로 보호 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security 프록시의 작동 방식에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 35a43120-bf67-4cf9-9b48-ebe157dbbd18
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 950ccd90c2efa777bc8f43abf87a2638f7316de1
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2018
---
# <a name="protect-apps-with-microsoft-cloud-app-security-proxy"></a>Microsoft Cloud App Security 프록시를 사용하여 앱 보호

> [!NOTE]
> 이것은 미리 보기 기능입니다.


요즘의 작업 공간에서는 사후에 클라우드 환경에 무슨 일이 일어났는지 아는 것만으로는 충분치 않습니다. 지금은 직원이 의도적이든 우연이든 데이터와 조직을 위험에 빠뜨리기 전에 위반이나 누수를 실시간으로 막을 수 있어야 합니다. 조직의 사용자가 클라우드 앱에서 제공하는 대부분의 서비스 및 도구를 최대한 활용하고 자신의 장치를 작동할 수 있도록 하는 것이 중요합니다. 동시에 데이터 누수 및 데이터 절도로부터 실시간으로 조직을 보호할 수 있는 도구가 필요합니다. Cloud App Security 프록시는 Azure Active Directory와 함께 전체적이고 통합된 환경에서 이러한 기능을 제공합니다.

## <a name="how-it-works"></a>작동 방식

Cloud App Security 프록시는 Azure AD 조건부 액세스와 통합됩니다. Azure AD 조건부 액세스를 사용하면 특정 조건에 따라 조직의 앱에 대한 액세스 제어를 적용할 수 있습니다. 조건은 *who*(예: 사용자 또는 사용자 그룹)와 *what*(클라우드 앱) 및 *where*(위치 및 네트워크) 조건부 액세스 정책이 적용됩니다. 조건을 결정한 후에 액세스 및 세션 컨트롤을 적용할 수 있는 Cloud App Security 프록시로 사용자를 라우팅할 수 있습니다.

사용자가 Cloud App Security 프록시로 라우팅되면 액세스 및 세션 정책에 따라 실시간으로 앱 액세스 및 세션을 모니터링하고 제어할 수 있습니다. 액세스 및 세션 정책은 Cloud App Security 포털에서 활용되어 필터를 자세히 구체화하고 사용자에 대해 수행할 작업을 설정합니다. 액세스 및 세션 정책을 사용하면 다음을 수행할 수 있습니다.

-   **다운로드 시 차단**: 중요한 문서의 다운로드를 차단할 수 있습니다. 예를 들어 관리되지 않는 장치에 다운로드하는 경우에는 차단됩니다.

-   **다운로드 시 보호**: 중요한 문서의 다운로드를 차단하는 대신 다운로드 시 암호화를 통해 문서를 보호하도록 요구할 수 있습니다. 이렇게 하면 데이터가 신뢰할 수 없는 장치에 다운로드되는 경우 문서가 보호되고 사용자 액세스가 인증됩니다. 

-   **비회사 네트워크의 사용자 세션 제한**: 회사 네트워크에 속하지 않은 위치에서 보호되는 앱에 액세스하는 사용자는 액세스가 제한되고 중요한 자료의 다운로드가 차단되거나 보호됩니다.

-   **낮은 신뢰 사용자 세션 모니터링**: 위험한 사용자가 앱에 로그인하고 해당 작업이 세션 내에서 기록될 때 모니터링됩니다. 사용자 동작을 조사하고 분석하여 나중에 세션 정책을 적용해야 하는 위치와 조건을 이해할 수 있습니다. 

- **액세스 차단**: 관리되지 않는 장치 또는 회사 네트워크가 아닌 곳의 사용자에 대해 특정 앱에 대한 액세스를 완전히 차단할 수 있습니다.


### <a name="how-session-control-works"></a>세션 제어 작동 방식

프록시의 세션 제어는 조건부 액세스를 기반으로 합니다. 앱에 대한 액세스를 제어한 후 사용자 세션을 앱으로 직접 리디렉션하지 않고 프록시의 세션 제어로 리디렉션할 수 있습니다. 이때부터 사용자 요청과 응답은 앱으로 직접 이동하는 것이 아니라 프록시를 통해 이동합니다.

세션 내에서 사용자를 유지하기 위해 프록시는 앱 세션 내에서 관련된 모든 URL, Java 스크립트 및 쿠키를 프록시 URL로 바꿉니다. 예를 들어 앱에서 도메인이 myapp.com으로 끝나는 링크가 포함된 페이지를 반환하는 경우 프록시는 연결을 myapp.com.us.cas.ms와 같이 끝나는 도메인으로 바꿉니다. 

이 방법을 사용하면 장치에 아무 것도 설치할 필요가 없습니다. 이는 관리되지 않는 장치에서 세션을 모니터링하는 경우에 가장 좋습니다. 

프록시를 통하도록 세션을 지정한 후에는 프록시에서 다음을 수행할 수 있습니다.
1. 사용자 활동에 대한 트래픽 검사
3. 클라우드 앱 프록시 포털에 식별된 활동 표시
2. 트래픽 로그 저장 및 분석
3. 관리자가 트래픽 로그를 내보낼 수 있도록 설정
4. 세션에서 정책 적용

## <a name="managed-device-identification"></a>관리 장치 식별

프록시를 사용하면 장치를 관리할지 여부를 고려하는 정책을 만들 수 있습니다. 장치를 관리하는지 여부를 확인하기 위해 프록시에서 다음을 활용합니다.

-   준수 장치 
-   도메인 가입 장치 
-   클라이언트 인증서 배포
 
 
### <a name="compliant-and-domain-joined-devices"></a>준수 및 도메인 가입 장치
Azure AD 조건부 액세스를 사용하면 준수 및 도메인 가입 장치 정보를 Cloud App Security 프록시에 직접 전달할 수 있습니다. 여기서 장치 상태를 필터로 사용하는 액세스 정책 또는 세션 정책을 개발할 수 있습니다.
자세한 내용은 [Azure Active Directory의 장치 관리 소개](https://docs.microsoft.com/azure/active-directory/device-management-introduction)를 참조하세요. 

### <a name="client-certificate-authenticated-devices"></a>클라이언트 인증서 인증 장치

프록시 장치 식별 메커니즘에서는 클라이언트 인증서를 사용하여 관련 장치에서 인증을 요청할 수 있습니다. 그러면 조직에 이미 배포된 기존 클라이언트 인증서를 활용하거나 관리 장치에 새 클라이언트 인증서를 배포한 다음 이러한 인증서의 존재를 사용하여 액세스 및 세션 정책을 설정할 수 있습니다. 클라이언트 인증서를 배포하는 방법에 대한 내용은 [Azure AD 앱용 프록시 배포](proxy-deployment-aad.md)를 참조하세요.
 
## <a name="supported-apps-and-clients"></a>지원되는 앱 및 클라이언트

프록시는 현재 Azure AD에서 SAML Single Sign-On으로 구성된 앱을 지원합니다. 

> [!NOTE]
> - 프록시는 비공개 미리 보기에서 Azure AD 이외의 ID 공급자로 구성된 앱도 지원합니다. 비공개 미리 보기에 대한 자세한 내용이 필요하면 mcaspreview@microsoft.com에 전자 메일을 보내주세요.
> - Office 365 응용 프로그램은 SAML로 구성되지 않으므로 현재 지원되지 않습니다.

또한 모든 앱에 대해 세션 제어를 자동으로 사용할 수 있는 것은 아닙니다. Cloud App Security 팀에서 세션 제어를 사용하여 인기 있는 많은 앱을 테스트했습니다. 다른 앱은 고객과 함께 수행되는 온보딩 프로세스가 필요할 수 있습니다.
클라이언트 측면에서 세션 제어는 주요 플랫폼의 모든 브라우저에서 사용할 수 있습니다. 그러나 모바일 앱과 데스크톱 앱은 세션 컨트롤에서 지원되지 않습니다. 



## <a name="see-also"></a>참고 항목  
[Cloud App Security 프록시 배포](proxy-deployment-aad.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  


