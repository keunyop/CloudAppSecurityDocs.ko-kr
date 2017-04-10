---
title: "Cloud App Security란? | Microsoft 문서"
description: "이 항목에서는 클라우드 응용 프로그램 보안 및 작동 방식을 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/2/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 041c22aea7ab20682cab199af2a0f17129cade3e
ms.sourcegitcommit: 8c7c25bc727d9c471261da144d5c1d430c26af56
translationtype: HT
---
# <a name="what-is-cloud-app-security"></a>Cloud App Security란?

> [!NOTE]
> Office 365의 고급 보안 관리 및 Cloud App Security 기능에 대한 자세한 내용은 [고급 보안 관리 시작](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a)을 참조하세요.

클라우드로 전환하면 직원들의 유연성이 증가하고 IT 비용이 감소하지만, 조직의 보안 유지 면에서는 새로운 복잡성과 문제도 발생합니다. 클라우드 응용 프로그램의 모든 이점을 얻으려면 IT 팀에서 제어를 유지하는 동시에 액세스를 허용하는 적절한 균형 지점을 찾아 중요한 데이터를 보호해야 합니다.  

Cloud App Security는 Microsoft Cloud Security 스택의 주요 구성 요소입니다. 조직이 클라우드 응용 프로그램의 기능을 모두 활용하는 방향으로 발전할 수 있게 도우면서도 활동에 대한 가시성을 향상시켜 제어를 유지하는 포괄적인 솔루션입니다. 또한 클라우드 응용 프로그램에서 중요한 데이터의 보호를 강화하는 데에도 도움이 됩니다. 섀도 IT를 찾는 데 유용한 도구를 사용하여 위험 평가, 정책 적용, 활동 조사 및 위협을 중지합니다. 조직은 중요한 데이터의 제어를 유지하면서도 더 안전하게 클라우드로 이동할 수 있습니다. 

## <a name="the-cloud-app-security-framework"></a>Cloud App Security 프레임워크  

- **Cloud Discovery**: 섀도 IT 보고와 제어 및 위험 평가를 포함하여 조직의 모든 클라우드 사용을 검색합니다.
    
- **데이터 보호**: 가시성을 확보하고 DLP 정책, 경고 및 조사를 적용하여 클라우드에서 데이터를 모니터링하고 제어합니다. 
    
- **위협 방지**: 비정상적인 사용 및 보안 인시던트를 감지합니다. 네트워크 클라우드 트래픽을 최대한 효과적으로 제어하기 위해 동작 분석 및 고급 조사 도구를 사용하여 위험을 완화하고 정책과 경고를 설정합니다.

## <a name="architecture"></a>아키텍처  

Cloud App Security는 다음과 같은 방법으로 클라우드에 가시성을 통합합니다.  

-   클라우드 검색을 사용하여 클라우드 환경 및 조직에서 사용 중인 클라우드 응용 프로그램을 매핑하고 식별합니다.
-   클라우드에서 응용 프로그램의 권한을 부여하고 취소합니다.  
-   배포가 쉬운 응용 프로그램 커넥터를 사용하여 API를 활용하고 연결하는 응용 프로그램의 가시성과 거버넌스를 확보합니다.  
-   정책을 설정한 후 지속적으로 미세 조정하여 연속 제어를 돕습니다.  

![Cloud App Security 아키텍처 다이어그램](./media/architecture.png)  

### <a name="data-retention--compliance"></a>데이터 보존 및 규정 준수

Cloud App Security는 ISO, HIPAA, CSA STAR, EU 모델 조항 등에 대한 Microsoft 규정 준수로 공식 인증되었습니다. 인증의 전체 목록을 보려면 [Microsoft 규정 준수 제안](https://go.microsoft.com/fwlink/?linkid=842039)으로 이동하고 Cloud App Security를 선택하세요.  

Cloud App Security가 콘텐츠 검사를 수행하면 데이터 개인 정보 보호가 적용됩니다. 파일 콘텐츠는 Cloud App Security 데이터베이스에 저장되지 않습니다. 파일 레코드의 메타데이터 및 확인된 위반만 Cloud App Security 데이터베이스에 저장됩니다. 데이터 보존에 대한 자세한 내용은 [개인 정보 취급 방침](http://go.microsoft.com/fwlink/?LinkId=512132) 및 [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data)를 참조하세요.
Cloud App Security에서는 다음과 같이 데이터를 유지합니다. 
 
- 활동 로그: 180일 
- 검색 데이터: 90일 
- 경고: 180일 

이러한 원본의 데이터를 수집한 후 Cloud App Security에서 데이터에 대한 정교한 분석을 실행 합니다. 비정상적인 활동이 있으면 즉시 알리고, 클라우드 환경에 대한 심층적인 정보를 제공합니다. Cloud App Security에서 정책을 구성한 다음 클라우드 환경에 있는 모든 항목을 보호하는 데 사용할 수 있습니다.  

### <a name="cloud-discovery"></a>클라우드 검색  

클라우드 검색은 트래픽 로그를 사용하여 조직에서 사용 중인 클라우드 응용 프로그램을 동적으로 검색하고 분석합니다. 조직의 클라우드 사용에 관한 스냅숏 보고서를 만들려면 분석을 위해 방화벽 또는 프록시에서 로그 파일을 수동으로 업로드할 수 있습니다. 지속적인 보고서를 설정하려면 Cloud App Security 로그 수집기를 사용하여 주기적으로 로그를 전달합니다.  

Cloud Discovery에 대한 자세한 내용은 [Cloud Discovery 설정](set-up-cloud-discovery.md)을 참조하세요.

### <a name="sanctioning-and-unsanctioning-an-app"></a>응용 프로그램 사용 권한 부여 및 취소  

Cloud App Security를 사용하면 *클라우드 응용 프로그램 카탈로그*를 통해 조직에 있는 응용 프로그램의 권한을 부여 또는 취소할 수 있습니다. Microsoft 분석가 팀은 산업 표준에 따라 순위 및 점수가 매겨진 13,000개 이상의 클라우드 앱을 포함하는 광범위한 카탈로그를 작성했으며 계속 확장하고 있습니다. 클라우드 응용 프로그램 카탈로그를 사용하여 규정 인증, 산업 표준 및 모범 사례에 따라 클라우드 응용 프로그램의 위험을 평가할 수 있습니다. 그리고 다양한 매개 변수의 점수와 가중치를 조직의 요구에 맞게 사용자 지정합니다. 이러한 점수를 기준으로 Cloud App Security에서 환경에 영향을 줄 수 있는 50개 이상의 위험 요소에 따라 응용 프로그램의 위험도를 확인할 수 있습니다.  

### <a name="app-connectors"></a>응용 프로그램 커넥터  
응용 프로그램 커넥터에서는 클라우드 응용 프로그램 공급자의 API를 사용하여 Cloud App Security 클라우드를 다른 클라우드 응용 프로그램과 통합합니다. 응용 프로그램 커넥터는 제어 및 보호를 확장합니다. 또한 Cloud App Security 분석을 위해 클라우드 응용 프로그램에서 직접 정보에 액세스할 수 있도록 합니다.  

응용 프로그램의 연결과 보호 강화를 위해, 응용 프로그램 관리자는 Cloud App Security에 응용 프로그램 액세스 권한을 부여합니다. 그런 다음, Cloud App Security에서 응용 프로그램의 활동 로그를 쿼리하고 데이터와 계정, 클라우드 콘텐츠를 검색합니다. Cloud App Security는 정책을 적용하고, 위험을 검색하며, 문제 해결을 위한 거버넌스 작업을 제공할 수 있습니다.  

Cloud App Security에서는 클라우드 제공자가 제공한 API를 사용합니다. 각 응용 프로그램에는 자체 프레임워크 및 API 제한이 있습니다. Cloud App Security는 앱 공급자와 함께 작동하여 API 사용을 최적화하고 최적의 성능을 보장합니다. 응용 프로그램이 API에 적용하는 다양한 제한을 고려하여(제한, API 제한, 동적 시간 이동 API 창 등), Cloud App Security 엔진은 허용된 용량을 활용합니다. 테넌트에 있는 모든 파일 검색 등의 일부 작업에는 대량 API가 필요하므로 보다 오랜 기간 동안에 분산됩니다. 일부 정책은 몇 시간 또는 며칠 동안 실행될 것으로 예상합니다.  

### <a name="policy-control"></a>정책 제어  

정책을 사용하여 클라우드에서의 사용자 동작을 정의할 수 있습니다. 정책을 사용하여 클라우드 환경에서 위험한 동작, 위반 또는 의심스러운 데이터 요소 및 활동을 검색합니다. 필요한 경우 정책을 사용하여 수정 프로세스를 통합하고 완전한 위험 완화를 달성할 수 있습니다. 여러 유형의 정책이 클라우드 환경에 대해 수집하려는 다양한 정보 유형 및 수행할 수 있는 수정 작업 유형과 상호 관련되어 있습니다.  

## <a name="see-also"></a>참고 항목  

[Cloud App Security 시작](getting-started-with-cloud-app-security.md)에서 기본적인 사항을 읽으세요.    
기술 지원을 받으려면 [Cloud App Security 보조 지원](http://support.microsoft.com/oas/default.aspx?prid=16031) 페이지를 방문하세요.   
프리미어 고객은 [프리미어 포털](https://premier.microsoft.com/)에서 직접 Cloud App Security를 선택할 수도 있습니다.   
