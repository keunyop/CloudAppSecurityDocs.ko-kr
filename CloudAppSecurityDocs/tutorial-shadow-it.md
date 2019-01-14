---
title: 섀도 IT 검색 및 관리 | Microsoft Docs
description: 이 자습서에서는 Microsoft Cloud App Security에서 Azure Information Protection 분류 레이블을 자동으로 적용하는 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/6/2019
ms.topic: tutorial
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3
ms.reviewer: dannyk
ms.suite: ems
ms.openlocfilehash: 3e31313739befa39b11853df971dd0c490884e07
ms.sourcegitcommit: 2a25d1af0560243d7f926c87bf56230bdf336ba9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54142287"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="tutorial-discover-and-manage-shadow-it-in-your-network"></a>자습서: 네트워크의 섀도 IT 검색 및 관리

IT 관리자에게 직원이 사용하는 클라우드 앱의 수를 질문할 때, 평균 30, 40개로 답하면 실제로는 조직의 직원이 평균 1,000개가 넘는 별도 앱을 사용하고 있습니다. 섀도 IT를 통해 사용 중인 앱과 위험 수준을 파악하고 식별할 수 있습니다. 직원의 80%는 아무도 검토한 적이 없는 사용 권한 없는 앱을 사용하며 보안 및 규정 준수 정책을 준수하지 않을 수 있습니다. 또한 직원이 회사 네트워크 외부에서 리소스 및 앱에 액세스할 수 있기 때문에 더 이상 방화벽에 규칙과 정책을 적용하는 것만으로는 충분하지 않습니다. 

이 자습서에서는 Cloud Discovery를 사용하여 사용 중인 앱을 검색하고, 이러한 앱의 위험을 탐색하고, 사용 중인 새 위험 앱을 식별하도록 정책을 구성하고, 프록시 또는 방화벽 어플라이언스를 사용하여 기본적으로 차단하기 위해 이러한 앱을 선택 취소하는 방법에 대한 지침을 제공합니다.

> [!div class="checklist"]
> * 섀도 IT 검색 및 식별
> * 평가 및 분석
> * 앱 관리
> * 사용 권한 앱 제어
 
## <a name="how-to-discover-and-manage-shadow-it-in-your-network"></a>네트워크에서 섀도 IT를 검색하고 관리하는 방법

이 프로세스를 사용하여 조직에서 섀도 IT Cloud Discovery를 배포합니다.

![섀도 IT 수명 주기](./media/shadow-it-lifecycle.png)

### <a name="phase-1-discover-and-identify-shadow-it"></a>1단계: 섀도 IT 검색 및 식별
    
1. **섀도 IT 검색**: 조직에서 Cloud Discovery를 실행하여 네트워크의 실제 상황을 확인함으로써 조직의 보안 상태를 식별합니다. 자세한 내용은 [클라우드 검색 설정](set-up-cloud-discovery.md)을 참조하세요. 이는 다음 방법 중 하나를 사용하여 수행할 수 있습니다.
  
    - Cloud App Security를 프록시와 통합합니다. Cloud App Security는 기본적으로 [Zscaler](zscaler-integration.md)를 비롯한 일부 타사 프록시와 통합됩니다.
    
    - [Windows Defender ATP](wdatp-integration.md)와의 통합을 통해 Cloud Discovery를 빠르게 시작하고 실행할 수 있습니다. 이 네이티브 통합을 통해 네트워크 켜고 끄기, Windows 10 디바이스 전반의 클라우드 트래픽에 대한 데이터 수집을 즉시 시작할 수 있습니다.
   
    - 네트워크에 연결된 모든 디바이스의 범위를 보려면 방화벽 및 기타 프록시에 [Cloud App Security 로그 수집기](discovery-docker.md)를 배포하여 엔드포인트에서 데이터 수집 및 분석을 위해 Cloud App Security로 보내는 것이 중요합니다.


정책은 사용자 그룹, 지역 및 비즈니스 그룹에 따라 다르므로 이러한 각 단위에 대한 섀도 IT 보고서를 만드는 것이 좋습니다. 자세한 내용은 (discovery-docker-windows#continuous-reports)를 참조하세요.


이제 네트워크에서 Cloud Discovery가 실행 중이므로 생성된 연속 보고서를 살펴보고 [Cloud Discovery 대시보드](working-with-cloud-discovery-data.md)를 확인하여 조직에서 사용 중인 앱의 전체 그림을 가져옵니다. 범주별로 확인하는 것이 좋습니다. 사용 권한 없는 앱이 사용 권한 앱으로 해결되지 않은 합법적인 업무 관련 목적에 사용되는 경우가 종종 있기 때문입니다. 

2. **앱의 위험 수준 식별**: Cloud App Security 클라우드 앱 카탈로그를 사용하여 검색된 각 앱과 관련된 위험을 자세히 파악합니다. Cloud App Security의 위험 카탈로그에는 70개가 넘는 위험 요소를 사용하여 평가되는 16,000개가 넘는 앱이 포함되어 있습니다. 위험 요소는 앱에 대한 일반 정보(게시자인 앱의 본사가 있는 곳)와 보안 조치 및 제어(휴면 상태의 암호화 지원, 사용자 작업에 대한 감사 로그 제공)를 통해 시작됩니다. 자세한 내용은 [위험 점수 사용](risk-score.md)을 참조하세요.
    
   - Cloud App Security 포털의 **검색** 아래에서 **검색된 앱**을 클릭합니다. 우려되는 위험 요소로 조직에서 사용 중인 것으로 검색된 앱 목록을 필터링합니다. 예를 들어 고급 필터를 사용하여 위험 점수가 8 미만인 모든 앱을 찾을 수 있습니다. 

   - 앱 이름을 클릭한 다음, **정보** 탭을 클릭하여 앱의 보안 위험 요소에 대한 세부 정보를 확인함으로써 앱의 규정 준수를 자세히 파악할 수 있습니다.
    
### <a name="phase-2-evaluate-and-analyze"></a>2단계: 평가 및 분석

1. **규정 준수 평가**: 앱이 HIPAA, SOC2 GDPR 등 조직의 표준을 준수하는 것으로 인증되었는지 확인합니다.
   - Cloud App Security 포털의 **검색** 아래에서 **검색된 앱**을 클릭합니다. 우려되는 규정 준수 위험 요소로 조직에서 검색된 앱 목록을 필터링합니다. 예를 들어 제안된 쿼리를 사용하여 비규격 앱을 필터링합니다.
   - 앱 이름을 클릭한 다음, **정보** 탭을 클릭하여 앱의 규정 준수 위험 요소에 대한 세부 정보를 확인함으로써 앱의 규정 준수에 대한 자세한 내용을 볼 수 있습니다.

2. **사용 현황 분석**: 이제 조직에서 앱을 사용할지 여부를 파악했으므로 누가 어떻게 사용하고 있는지 조사하려고 합니다. 조직에서 제한된 방식으로만 사용하는 경우 괜찮을 수 있지만, 사용량이 증가하는 경우에는 알림을 받아서 앱을 차단할지를 결정할 수 있습니다.
    - Cloud App Security 포털의 **검색** 아래에서 **검색된 앱**을 클릭한 다음, 조사할 특정 앱을 클릭하여 드릴다운합니다. **사용** 탭에서는 앱을 사용하는 활성 사용자 수와 생성되는 트래픽 양을 알 수 있습니다. 이는 이미 앱의 상황을 파악할 수 있는 상당히 좋은 그림을 줄 수 있습니다. 그런 다음, 특히 앱을 사용하는 사용자를 확인하려면 **총 활성 사용자**를 클릭하여 추가로 드릴다운하면 됩니다. 이 중요한 단계는 관련 정보를 제공할 수 있습니다. 예를 들어 특정 앱의 모든 사용자가 마케팅 부서에서 온 것으로 검색된 경우, 이 앱에 대한 비즈니스 필요성이 있을 수 있고, 위험하다면 그것을 차단하기 전에 대안에 대해 논의해야 합니다.

4. 동일한 앱 범주에 속하는 앱과 조직의 정책을 준수하는 데 필요한 다양한 보안 제어를 준수하는 고급 필터 식별 솔루션을 사용하여 클라우드 앱 카탈로그 및 필터를 사용합니다.


### <a name="phase-3-manage-your-apps"></a>3단계: 앱 관리
    
- **클라우드 앱 관리**: Cloud App Security는 조직에서 앱 사용을 관리하는 프로세스를 지원합니다. 조직에서 사용되는 다양한 패턴과 동작을 식별한 후에는 해당 비즈니스 상태 또는 근거에 따라 각 앱을 분류하기 위해 새 사용자 지정 앱 태그를 만들 수 있습니다.
그런 다음, 이러한 태그를 특정 목적으로 사용할 수 있습니다(예: 위험한 클라우드 스토리지 앱으로 태그가 지정된 앱으로 이동하는 높은 트랙픽 식별). 앱 태그는 **Cloud Discovery 설정** > **앱 태그**에서 관리할 수 있습니다. 그런 다음, 이러한 태그를 나중에 Cloud Discovery 페이지에서 필터링하고 이를 사용하여 정책을 생성하는 데 사용할 수 있습니다.
    
이제 정책을 만들어 걱정되는 사항이 발생하면 자동으로 경고를 받을 수 있도록 합니다. 예를 들어 우려되는 앱의 다운로드 또는 트래픽이 급증하는 시기를 알 수 있도록 **앱 검색 정책**을 만들 수 있습니다. 이메일 또는 문자 메시지로 알리는 정책을 설정할 수 있습니다. 자세한 내용은 [정책 템플릿 참조](policy-template-reference.md) 및 [Cloud Discovery 정책](cloud-discovery-policies.md)에 대한 추가 정보를 참조하세요.

- **연속 모니터링**: 이제 앱에 대해 자세히 조사했으므로, 앱을 모니터링하고 필요한 경우 제어 기능을 제공하는 정책을 설정할 수 있습니다.


[**앱 검색 정책**](cloud-discovery-policies.md)을 구성합니다. 예를 들어 **검색된 사용자의 비정상 동작**, **클라우드 스토리지 앱 규정 준수 확인** 및 **위험한 새 앱**을 사용하도록 설정해야 합니다.


경고 페이지를 살펴보고 **정책 유형** 필터를 사용하여 앱 검색 경고를 확인합니다. 앱 검색 정책과 일치하는 앱의 경우, 예를 들어 앱 사용자에게 문의하여 앱 사용에 대한 비즈니스 근거에 대해 자세히 알아보려면 고급 조사를 수행하는 것이 좋습니다. 그런 다음, 2단계의 단계를 반복하여 앱의 위험을 평가합니다. 그런 다음, 나중에 애플리케이션의 사용을 승인하거나 나중에 사용자가 액세스할 때 애플리케이션을 차단할지 여부에 관계없이 다음 단계를 결정합니다. 이 경우 방화벽, 프록시 또는 보안 웹 게이트웨이를 사용하여 차단될 수 있도록 사용 권한 없는 것으로 태그를 지정해야 합니다. 


### <a name="phase-4-control-sanctioned-apps"></a>4단계: 사용 권한 앱 제어

1. API를 통해 앱 제어를 사용하도록 설정하려면 연속 모니터링에 대해 [API 통해 앱을 연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)(enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)합니다.

2. [조건부 액세스 앱 제어](proxy-intro-aad.md)를 사용하여 앱을 보호합니다.


클라우드 앱의 특성은 매일 업데이트되고 새 앱이 항상 표시된다는 것을 의미합니다. 이러한 이유로 직원은 지속적으로 새 앱을 사용하고 있으며 정책 추적, 검토 및 업데이트하고 사용자가 사용 중인 앱과 사용 패턴 및 동작 패턴을 확인하는 것이 중요합니다. 항상 Cloud Discovery 대시보드로 이동하여 사용 중인 새 앱을 확인하고 이 문서의 지침에 따라 조직과 데이터가 보호되는지 다시 확인할 수 있습니다.


## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  