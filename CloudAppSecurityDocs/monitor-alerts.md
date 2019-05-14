---
title: Cloud App Security에서 발생한 경고 모니터링
description: 이 문서에서는 모든 경고에 대해 목록 및 설명을 제공합니다.
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
ms.assetid: f118a3bf-1663-46ba-884f-b1b03a84ab66
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: e5b144b4c260aa55f3bd6546f76c1802c10631e0
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568905"
---
# <a name="monitor-alerts-in-cloud-app-security"></a>Cloud App Security의 경고 모니터링

*적용 대상: Microsoft Cloud App Security*

경고는 클라우드 환경을 보다 자세히 이해하기 위한 진입점입니다. 이 문서에서는 모든 경고에 대해 목록 및 설명을 제공합니다.

## <a name="monitoring-your-alerts"></a>경고 모니터링

모든 경고를 검토하는 것이 좋습니다. 경고가 발생하는 이유를 이해하면 정책을 수정하기 위한 도구로 사용할 수 있습니다. 

**경고를 보려면:** Microsoft Cloud App Security 포털에서 **경고**를 클릭합니다.


![경고 메뉴](./media/alert-menu.png)

 - 살펴본 후 경고를 **해제**하고 관심 없는 것으로 결정합니다. 
     - **주석**을 입력하여 경고를 해제한 이유를 설명합니다. 
     - 경고를 개선하기 위해 보안 연구 팀에서 검토하도록 **이 경고에 대한 의견을 보내주세요**.

- 경고를 조사하고 위험을 완화하는 경우 경고를 **해결**합니다. 

     - 경고가 더 이상 경고 테이블에 표시되지 않습니다.
     - 문제를 조사하기 시작했지만 계속 작업하기 위해 기억해 두려는 경우 **읽지 않은 상태로 표시**합니다. 
     -  향후 경고 일치 항목을 향상하려면 경고와 일치하는 **정책을 조정**합니다. 
     - 경고를 해결하면 주석을 입력하는 옵션이 제공되며 **Cloud App Security 팀에 피드백을 보냅니다**.
 
## <a name="built-in-alerts"></a>기본 제공 경고

다음과 같은 경고 유형이 표시됩니다. 

|경고 이름|AlertID|Description|
|----|----|----|
|새 위치|ALERT_GEOLOCATION_NEW_COUNTRY|검색이 시작된 이후(최대 6개월) 새 위치가 검색되었습니다. 이 경고는 전체 조직의 각 국가에 대해 한 번만 표시됩니다. |
|새 관리자|ALERT_ADMIN_USER|특정 앱에 대해 새 관리자가 검색되었습니다. 이는 한 애플리케이션에서 관리자이면서 이제 다른 애플리케이션에서도 관리자인 사람일 수 있습니다. 이 경고는 특정 관리 유형과 관련되므로 관리 유형이 변경될 때마다 표시됩니다. 사용자가 관리자 권한을 잃었다가 다시 얻게 되면 이 경고가 표시됩니다.|
|비활성 계정|ALERT_ZOMBIE_USER|사용자가 애플리케이션별로 60일 동안 비활성 상태인 경우입니다. 예를 들어 Box에서는 활성 상태이지만 60일 동안 G Suite를 터치하지 않은 경우 사용자는 G Suite에서 비활성으로 간주됩니다. 이러한 사용자에게는 태그가 추가되어 비활성 계정을 검색할 수 있습니다.|
|예기치 않은 관리자 위치|ALERT_NEW_ADMIN_LOCATION|검색이 시작된 이후(최대 6개월) 관리자에 대해 새 위치가 검색되었습니다. 이 경고는 전체 조직 모든 관리자의 각 국가에 대해 한 번만 표시됩니다. |
|손상된 계정|ALERT_COMPROMISED_ACCOUNT|애플리케이션에서 위반이 발생한 경우 위반한 계정 목록이 게시되면 Cloud App Security에서 해당 목록을 다운로드하여 사용자 목록과 비교합니다. 사용자 목록은 내부 사용자, 외부 사용자 및 개인 계정을 포함합니다. |

## <a name="custom-alerts"></a>사용자 지정 경고

다음과 같은 경고 유형이 표시됩니다. 

|경고 이름|AlertID|Description|
|----|----|----|
|의심스러운 활동 경고|ALERT_SUSPICIOUS_ACTIVITY|의심스러운 활동은 비정상적인 활동이 얼마나 의심스러운지 즉, 비활성 계정이 관련되어 있는지, 새 위치에서 시작되는지 등에 따라서 점수가 매겨집니다. 이러한 조건은 모두 함께 계산되어 다음과 같은 위험 요소를 기준으로 위험 점수를 제공합니다. <br>사용자가 관리자임 <br>엄격한 원격 사용자<br>익명 프록시<br> 전체 세션이 실패한 로그인임<br>다양한 실패한 로그인<br>새 요소(관리자)<br>IP/ISP/국가/사용자에 대한 사용자 에이전트/테넌트<br> IP/ISP/국가/(관리자) 사용자만 사용하는 사용자 에이전트<br>잠시 동안의 첫 번째 (관리자) 사용자 활동<br>이 특정 관리 활동이 처음으로 잠시 수행된 경우<br>이 특정 관리 활동이 일반적이지 않은 경우/이전에 수행되지 않은 경우<br>이전에 이 IP에 실패한 로그인만 있는 경우<br>이동 불가능|
|의심스러운 클라우드 사용 경고|ALERT_DISCOVERY_ANOMALY_DETECTION|Cloud Discovery 변칙 검색에서는 일반적인 동작의 패턴을 확인하고 비정상적인 방식으로 사용되는 사용자나 앱을 찾습니다. |
|활동 정책 위반|ALERT_CABINET_EVENT_MATCH_AUDIT|이 경고를 통해 정책 일치가 검색되었음을 알 수 있습니다.|
|파일 정책 위반|ALERT_CABINET_EVENT_MATCH_FILE|이 경고를 통해 정책 일치가 검색되었음을 알 수 있습니다.|
|프록시 정책 위반|ALERT_CABINET_INLINE_EVENT_MATCH|이 경고를 통해 정책 일치가 검색되었음을 알 수 있습니다.|
|필드 정책 위반|ALERT_CABINET_EVENT_MATCH_OBJECT|이 경고를 통해 정책 일치가 검색되었음을 알 수 있습니다.|
|새 서비스 검색됨|ALERT_CABINET_DISCOVERY_NEW_SERVICE|새 앱이 검색되었습니다.|
|개인 계정 사용|ALERT_PERSONAL_USER_SAGE|파일 공유 및 사용자 이름을 기반으로 검색 엔진에서 개인 계정을 검색합니다. |

## <a name="next-steps"></a>다음 단계 

[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
