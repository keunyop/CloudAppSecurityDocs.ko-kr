---
title: 클라우드 앱 활동 보기 | Microsoft 문서
description: 이 항목에서는 활동 정책에 적용할 수 있는 활동, 필터 및 일치 매개 변수 목록을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c80a67b0daa9191764528c0fcc2ed8fe5795541a
ms.sourcegitcommit: 0d73d21f961dc883f01a329bcf16dcaf070dca2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2018
ms.locfileid: "34559079"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="activities"></a>활동
Microsoft Cloud App Security에서는 연결된 앱의 모든 활동을 파악할 수 있습니다. 앱 커넥터를 사용해 앱에 Cloud App Security를 연결하면 Cloud App Security에서 수행된 모든 활동이 검색됩니다. 소급 검색 기간은 앱에 따라 다르며 계속 새 활동으로 업데이트됩니다. 

> [!NOTE] 
> Cloud App Security에 의해 모니터링되는 Office 365 활동의 전체 목록은 [Office 365 보안 및 준수 센터에서 감사 로그 검색](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities)을 참조하세요.

**활동 로그**를 필터링하여 특정 활동을 찾을 수 있습니다. 활동을 기준으로 정책을 만든 다음 경고를 받을 활동 및 조치를 정의할 수 있습니다. 특정 파일에 대해 수행된 활동을 검색할 수도 있습니다. 활동의 유형과 각 활동에 대해 가져오는 정보는 앱과 앱이 제공할 수 있는 데이터 종류에 따라 다릅니다. 

예를 들어 다음과 같이 **활동 로그**를 사용하여 조직에서 오래된 운영 체제나 브라우저를 사용하는 사용자를 찾을 수 있습니다. **활동 로그** 페이지에서 앱을 Cloud App Security에 연결한 후 고급 필터를 사용하여 **사용자 에이전트 태그**를 선택합니다. 그런 다음 **오래된 브라우저** 또는 **오래된 운영 체제**를 선택합니다.

 ![활동 오래된 브라우저 예제](media/activity-example-outdated.png)
 
기본 필터는 활동 필터링을 시작하기에 좋은 도구를 제공합니다.

 ![기본 활동 로그 필터](media/activity-log-filter-basic.png)

더 구체적인 활동으로 드릴다운하려면 [고급]을 클릭하여 기본 필터를 확장합니다.

 ![고급 활동 로그 필터](media/activity-log-filter-advanced.png)

> [!NOTE] 
> 레거시 태그는 이전 “사용자” 필터를 사용하는 모든 활동 정책에 추가됩니다. 이 필터는 평소대로 계속 작동합니다. 레거시 태그를 제거하려는 경우 필터를 제거하고 새 **사용자 이름** 필터를 사용하여 필터를 다시 추가할 수 있습니다.
 
## <a name="the-activity-drawer"></a>활동 서랍

### <a name="working-with-the-activity-drawer"></a>활동 서랍 사용

활동 로그에서 활동 자체를 클릭하여 각 활동에 관한 자세한 정보를 볼 수 있습니다. 그러면 각 활동에 대한 다음과 같은 추가 작업 및 정보를 제공하는 활동 서랍이 열립니다.
    - 일치 정책: 이 활동과 일치하는 정책의 목록을 보려면 [일치 정책] 링크를 클릭합니다.
    - 원시 데이터 보기: 응용 프로그램에서 받은 실제 데이터를 보려면 [원시 데이터 보기]를 클릭합니다.
    - 사용자: 사용자 페이지에서 활동을 수행한 사용자를 보려면 사용자를 클릭합니다. 
    - 장치 유형: 원시 사용자 에이전트 데이터를 보려면 장치 유형을 클릭합니다. 
    - 위치:Bing 지도에서 위치를 보려면 위치를 클릭합니다.
    - IP 주소 범주 및 태그: 이 활동에서 찾을 수 있는 IP 태그의 목록을 보려면 IP 태그를 클릭합니다. 그 후에 이 태그와 일치하는 모든 활동을 필터링할 수 있습니다.    

 활동 서랍의 필드는 추가 작업에 대한 상황별 링크 및 서랍에서 직접 수행할 수 있는 드릴다운을 제공합니다. 예를 들어 IP 주소 범주 옆으로 커서를 이동하면 필터에 추가 아이콘(![필터에 추가](./media/add-to-filter-icon.png))을 사용하여 현재 페이지의 필터에 IP 주소를 즉시 추가할 수 있습니다. 또한 설정 톱니 아이콘(![설정 아이콘](./media/contextual-settings-icon.png))을 사용하면 **사용자 그룹**과 같은 필드 중 하나의 구성을 수정하는 데 필요한 설정 페이지가 표시되므로 바로 작업할 수 있습니다.

 또한 탭 상단의 아이콘을 사용하여 다음 작업을 수행할 수 있습니다.
 - 동일한 유형의 활동 보기
 - 동일한 사용자의 모든 활동 보기
 - 동일한 IP 주소의 활동 보기
 - 동일한 지리적 위치의 활동 보기
 - 동일한 기간(48시간)의 활동 보기
 
![활동 서랍](./media/activity-drawer.png "활동 서랍")  
  
사용할 수 있는 거버넌스 작업 목록은 [활동 거버넌스 작업](governance-actions.md#activity-governance-actions)을 참조하세요.

#### <a name="user-insights"></a>사용자 정보

조사 환경에는 작업 사용자에 대한 기본 제공 정보가 포함됩니다. 한 번 클릭으로 사용자 연결이 시작된 위치, 사용자가 관련된 열린 경고 수, 사용자의 메타데이터 정보를 포함하여 사용자에 대한 포괄적인 개요를 확인할 수 있습니다.

사용자 정보를 보려면:

1. **활동 로그**에서 활동 자체를 클릭합니다.

2. 그다음에 **사용자** 탭을 클릭합니다. <br></br> 그러면 활동 서랍이 열리고 **사용자** 탭에 사용자에 대한 다음 정보가 제공됩니다.
    - **열린 경고**: 사용자에 관련된 열린 경고 수입니다.
    - **파일 위반**: 사용자가 소유한 파일에 대한 파일 위반 수입니다.
    - **활동**: 지난 30일 동안 사용자가 수행한 활동 수입니다.
    - **국가**: 지난 30일 동안 사용자가 연결한 국가 수입니다.
    - **ISP**: 지난 30일 동안 사용자가 연결한 ISP 수입니다.
    - **IP 주소**: 지난 30일 동안 사용자가 연결한 IP 주소 수입니다.

![Cloud App Security에서의 사용자 정보](./media/user-insights.png)

#### <a name="ip-address-insights"></a>IP 주소 정보

IP 주소 정보는 거의 모든 조사에 매우 중요하므로 활동 서랍에서 IP 주소에 대한 자세한 정보를 볼 수 있습니다. 특정 활동 내에서 IP 주소 탭을 클릭하면 특정 IP 주소의 미해결 경고, 최근 활동의 추세 그래프, 위치 맵 등 해당 IP 주소에 대한 통합 데이터를 볼 수 있습니다. 이를 통해 쉽게 드릴다운할 수 있습니다. 예를 들어 불가능한 여행 경고를 조사할 때 IP 주소가 어디에 사용되었는지와 의심스러운 활동과 관련되어 있는지를 쉽게 알 수 있습니다. IP 주소를 위험, VPN 또는 회사로 지정할 수 있게 하는 IP 주소 서랍에서 작업을 바로 수행함으로써 향후 조사와 정책 만들기를 쉽게 수행할 수도 있습니다.

IP 주소 정보를 보려면:

1. **활동 로그**에서 활동 자체를 클릭합니다.

2. 그런 다음 **IP 주소** 탭을 클릭합니다. <br></br> 그러면 활동 서랍 **IP 주소** 탭이 열리고, 해당 탭에서는 IP 주소에 대한 다음 정보를 제공합니다.
    - **열린 경고**: IP 주소와 관련된 미해결 경고 수입니다.
    - **활동**: 지난 30일 동안 IP 주소가 수행한 활동 수입니다.
    - **IP 위치**: 지난 30일 동안 IP 주소가 연결된 지리적 위치입니다.
    - **활동**: 지난 30일 동안 이 IP 주소에서 수행된 활동 수입니다.
    - **관리자 활동**: 지난 30일 동안 이 IP 주소에서 수행된 관리 활동 수입니다.
    - 다음 IP 주소 작업을 수행할 수 있습니다.
        - 위험한 태그로 지정 
        - VPN IP 주소로 태그 지정
        - 위험한 IP로 태그 지정 후 차단된 그룹에 추가


![Cloud App Security에서의 IP 주소 정보](./media/ip-address-insights.png)

## 활동 내보내기 <a name="export"></a>

모든 사용자 활동을 CSV 파일로 내보낼 수 있습니다. 

**활동 로그**에서 오른쪽 위 모서리에 있는 **내보내기** 단추 ![내보내기 단추](./media/export-button.png)를 클릭합니다.

[!INCLUDE [Handle personal data](../includes/gdpr-intro-sentence.md)]



## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  