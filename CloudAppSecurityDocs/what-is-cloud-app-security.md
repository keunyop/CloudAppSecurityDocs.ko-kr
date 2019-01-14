---
title: Cloud App Security란?
description: 이 문서에서는 Microsoft Cloud App Security 및 작동 방식을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/7/2019
ms.topic: overview
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 4e049ead1d211d9e22668e18aec23293ee26dd59
ms.sourcegitcommit: 076705cc9684fe5fb35c33a51e3319ba2ccfd24e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2019
ms.locfileid: "54060159"
---
# <a name="microsoft-cloud-app-security-overview"></a>Microsoft Cloud App Security 개요

*적용 대상: Microsoft Cloud App Security*

> [!NOTE]
> Office 365 Cloud App Security에 대한 자세한 내용은 [Office 365 Cloud App Security](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a)을 참조하세요.

클라우드로 전환하면 직원의 유연성이 증가하고 IT 비용이 감소합니다. 그러나 조직을 보호하기 위한 새로운 과제 및 복잡성에 대해서도 소개합니다. 클라우드 애플리케이션의 모든 혜택을 받으려면 IT 팀에서 제어를 유지하는 동시에 액세스를 허용하는 적절한 균형 지점을 찾아 중요한 데이터를 보호해야 합니다.  

Cloud App Security는 Microsoft Cloud Security 스택의 주요 구성 요소입니다. 조직이 클라우드 애플리케이션의 기능을 모두 활용하는 방향으로 발전할 수 있게 도우면서도 활동에 대한 가시성을 향상시켜 제어를 유지하는 포괄적인 솔루션입니다. 또한 클라우드 애플리케이션에서 중요한 데이터의 보호를 강화하는 데에도 도움이 됩니다. 섀도 IT를 찾는 데 유용한 도구를 사용하여 위험 평가, 정책 적용, 활동 조사 및 위협을 중지합니다. 조직은 중요한 데이터의 제어를 유지하면서도 더 안전하게 클라우드로 이동할 수 있습니다. 

## <a name="the-cloud-app-security-framework"></a>Cloud App Security 프레임워크  

- **Cloud Discovery**: Shadow IT 보고와 제어 및 위험 평가를 포함하여 조직의 모든 클라우드 사용을 검색합니다.

- **데이터 보호**: 가시성을 확보하고 DLP 정책, 경고 및 조사를 적용하여 클라우드에서 데이터를 모니터링하고 제어합니다. 

- **위협 방지**: 비정상적인 사용 및 보안 인시던트를 감지합니다. 네트워크 클라우드 트래픽을 최대한 효과적으로 제어하기 위해 동작 분석 및 고급 조사 도구를 사용하여 위험을 완화하고 정책과 경고를 설정합니다.

## <a name="architecture"></a>아키텍처  

Cloud App Security는 다음과 같은 방법으로 클라우드에 가시성을 통합합니다.  

- Cloud Discovery를 사용하여 클라우드 환경 및 조직에서 사용 중인 클라우드 앱을 매핑하고 식별합니다.
- 클라우드에서 앱의 권한을 부여하고 취소합니다.  
- 배포가 쉬운 앱 커넥터를 사용하여 API를 활용하고 연결하는 앱의 가시성과 거버넌스를 확보합니다.  
- 조건부 액세스 앱 제어 보호를 사용하여 클라우드 앱 내에서 수행되는 액세스와 작업에 대한 실시간 가시성과 제어를 실현합니다.
- 정책을 설정한 다음, 지속적으로 미세 조정하여 연속 제어를 돕습니다.  

![Cloud App Security 아키텍처 다이어그램](./media/proxy-architecture.png)  

### <a name="data-retention--compliance"></a>데이터 보존 및 준수

Microsoft Cloud App Security 데이터 보존 및 준수에 대한 자세한 내용은 [Microsoft Cloud App Security 데이터 보안 및 개인 정보](cas-compliance-trust.md)를 참조하세요.

### <a name="cloud-discovery"></a>클라우드 검색  

클라우드 검색은 트래픽 로그를 사용하여 조직에서 사용 중인 클라우드 응용 프로그램을 동적으로 검색하고 분석합니다. 조직의 클라우드 사용에 관한 스냅숏 보고서를 만들려면 분석을 위해 방화벽 또는 프록시에서 로그 파일을 수동으로 업로드할 수 있습니다. 지속적인 보고서를 설정하려면 Cloud App Security 로그 수집기를 사용하여 주기적으로 로그를 전달합니다.  

Cloud Discovery에 대한 자세한 내용은 [Cloud Discovery 설정](set-up-cloud-discovery.md)을 참조하세요.

### <a name="sanctioning-and-unsanctioning-an-app"></a>응용 프로그램 사용 권한 부여 및 취소  

Cloud App Security를 사용하면 *클라우드 응용 프로그램 카탈로그*를 통해 조직에 있는 응용 프로그램의 권한을 부여 또는 취소할 수 있습니다. Microsoft 분석가 팀은 산업 표준에 따라 순위 및 점수가 매겨진 16,000개 이상의 클라우드 앱을 포함하는 광범위한 카탈로그를 작성했으며 계속 확장하고 있습니다. 클라우드 응용 프로그램 카탈로그를 사용하여 규정 인증, 산업 표준 및 모범 사례에 따라 클라우드 응용 프로그램의 위험을 평가할 수 있습니다. 그리고 다양한 매개 변수의 점수와 가중치를 조직의 요구에 맞게 사용자 지정합니다. 이러한 점수에 따라 Cloud App Security에서는 앱의 위험 정도를 알려줍니다. 점수 매기기는 환경에 영향을 줄 수 있는 70개가 넘는 위험 요소를 기반으로 합니다.  

### <a name="app-connectors"></a>응용 프로그램 커넥터

응용 프로그램 커넥터에서는 클라우드 응용 프로그램 공급자의 API를 사용하여 Cloud App Security 클라우드를 다른 클라우드 응용 프로그램과 통합합니다. 응용 프로그램 커넥터는 제어 및 보호를 확장합니다. 또한 Cloud App Security 분석을 위해 클라우드 응용 프로그램에서 직접 정보에 액세스할 수 있도록 합니다.  

응용 프로그램의 연결과 보호 강화를 위해, 응용 프로그램 관리자는 Cloud App Security에 응용 프로그램 액세스 권한을 부여합니다. 그런 다음, Cloud App Security에서 응용 프로그램의 활동 로그를 쿼리하고 데이터와 계정, 클라우드 콘텐츠를 검색합니다. Cloud App Security는 정책을 적용하고, 위험을 검색하며, 문제 해결을 위한 거버넌스 작업을 제공할 수 있습니다.  

Cloud App Security에서는 클라우드 제공자가 제공한 API를 사용합니다. 각 응용 프로그램에는 자체 프레임워크 및 API 제한이 있습니다. Cloud App Security는 앱 공급자를 사용하여 API 사용을 최적화하고 최적의 성능을 보장합니다. 응용 프로그램이 API에 적용하는 다양한 제한을 고려하여(제한, API 제한, 동적 시간 이동 API 창 등), Cloud App Security 엔진은 허용된 용량을 활용합니다. 테넌트에 있는 모든 파일 검색 등의 일부 작업에는 많은 API가 필요하므로 보다 오랜 기간 동안에 분산됩니다. 일부 정책은 몇 시간 또는 며칠 동안 실행될 것으로 예상합니다.  

### <a name="conditional-access-app-control-protection"></a>조건부 액세스 앱 제어 보호

Microsoft Cloud App Security 조건부 액세스 앱 제어는 역방향 프록시 아키텍처를 활용하여 클라우드 환경 내에서 수행되는 작업에 대한 실시간 가시성 및 제어를 위해 필요한 도구를 제공합니다. 조건부 액세스 앱 제어를 사용하면 다음과 같이 조직을 보호할 수 있습니다.

- 다운로드가 시작되기 전에 차단하여 데이터 누수 방지
- 안에 저장한 데이터와 클라우드에서 다운로드한 데이터를 암호화로 보호하도록 적용하는 규칙 설정
- 관리되지 않는 디바이스에서 수행되는 작업을 모니터링할 수 있도록 보호되지 않는 엔드포인트를 세부적으로 파악
- 비회사 네트워크 또는 위험한 IP 주소로부터의 액세스 제어

### <a name="policy-control"></a>정책 제어  

정책을 사용하여 클라우드에서의 사용자 동작을 정의할 수 있습니다. 정책을 사용하여 클라우드 환경에서 위험한 동작, 위반 또는 의심스러운 데이터 요소 및 활동을 검색합니다. 필요한 경우 정책을 사용하여 수정 프로세스를 통합하고 완전한 위험 완화를 달성할 수 있습니다. 여러 형식의 정책은 클라우드 환경에서 수집하려는 다양한 정보 유형 및 수행할 수 있는 수정 작업 형식과 상호 관련되어 있습니다.  

## <a name="related-videos"></a>관련 동영상

- [보안 커뮤니티에 가입](https://channel9.msdn.com/Shows/Microsoft-Security/Join-the-Security-Community)

## <a name="next-steps"></a>다음 단계  

[Cloud App Security 시작](getting-started-with-cloud-app-security.md)에서 기본적인 사항을 읽으세요.    

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)   