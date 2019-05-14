---
title: Microsoft Cloud App Security 배포 범위 지정
description: 이 문서에서는 특정 사용자 또는 그룹의 포함 및 제외를 비롯하여 Cloud App Security 배포 범위를 지원하는 방법에 대한 정보를 제공합니다.
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
ms.assetid: fe2ce27b-1020-45e9-ad72-fad93d197169
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: c1bd96bd60cd1170b9283ff19e35369193872c36
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568882"
---
# 범위 지정 배포 <a name="scoped-deployment"></a> 

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security를 사용하여 배포 범위를 지정할 수 있습니다. 범위 지정을 통해 앱에 대해 모니터링하거나 모니터링에서 제외할 특정 사용자 그룹을 선택할 수 있습니다.

## <a name="include-or-exclude-user-groups"></a>사용자 그룹 포함 또는 제외

조직의 모든 사용자에 대해 Microsoft Cloud App Security를 사용하고 싶지는 않을 수 있습니다. 범위 지정은 라이선스 제한으로 인해 배포를 제한하려는 경우에 특히 유용합니다. 특정 국가의 사용자를 모니터링하지 않아도 되는 규정 준수 규정으로 인해 제한해야 할 수도 있습니다. 예를 들어 범위 지정 배포를 사용하여 미국 기반 직원만 모니터링합니다. 또는 독일에 기반을 둔 사용자의 활동을 표시하지 않을 수 있습니다.

- 배포 범위를 지정하려면 먼저 Microsoft Cloud App Security로 [사용자 그룹을 가져와야](user-groups.md) 합니다. 기본적으로 다음과 같은 그룹이 표시됩니다.
    - **애플리케이션** 사용자 그룹 - Office 365 및 Azure AD 애플리케이션에서 수행되는 작업을 볼 수 있는 기본 제공 그룹입니다.
    - **외부 사용자** 그룹 - 조직에 대해 설정한 [IP 주소 범위](ip-tags.md) 내에 있지 않은 모든 사용자입니다.
- 포함 규칙을 설정하면 포함된 그룹에 속하지 않는 모든 그룹이 자동으로 제외됩니다. 예를 들어 미국 사무소 그룹의 모든 구성원을 포함하기 위한 규칙을 설정하면 해당 그룹에 속하지 않는 모든 그룹은 모니터링되지 않습니다.
- 제외된 사용자 그룹은 포함된 사용자 그룹을 재정의합니다. 즉, 사용자 그룹 “영국 직원”을 포함하지만 “마케팅”을 제외하는 경우, 영국의 마케팅 구성원은 **영국 직원** 그룹의 구성원인 경우에도 모니터링되지 않습니다.

1. 메뉴 모음에서 설정 코그를 클릭하고 **범위 지정 배포**를 선택합니다.  

    ![설정 아이콘](./media/settings-icon.png "설정 아이콘")

2. 특정 그룹을 포함하거나 제외하는 배포 범위를 지정하려면 먼저 Microsoft Cloud App Security로 [사용자 그룹을 가져와야](user-groups.md) 합니다. 

3. Microsoft Cloud App Security에서 모니터링할 특정 그룹을 설정하려면 **포함** 탭에서 더하기 아이콘를 클릭합니다. 
    ![아이콘](./media/plus-icon.png)

4. **새 포함 규칙 만들기** 대화 상자에서 다음 단계를 수행합니다.

    1. **Type rule name**(규칙 이름 입력) 아래에 규칙에 대한 설명이 포함된 이름을 지정합니다.
    2. **사용자 그룹 선택** 아래에서 Cloud App Security로 모니터링할 모든 그룹을 선택합니다.
    3. 이 규칙을 연결된 모든 앱에 적용할지 또는 **특정 앱**에만 적용할지 선택합니다. **특정 앱**을 선택하는 경우 규칙은 선택한 앱의 모니터링에만 영향을 줍니다. 예를 들어 그룹 **UI 팀 사용자** 및 **상자**를 선택하면 Cloud App Security는 UI 팀 사용자 그룹과 다른 모든 앱에 대한 상자 활동만 모니터링하고, Cloud App Security는 모든 사용자의 모든 활동을 모니터링합니다.
     
        ![포함 규칙](./media/include-rule.png)

5. 모니터링에서 제외할 특정 그룹을 설정하려면 **제외** 탭에서 더하기 아이콘을 클릭합니다. 
    
   ![아이콘](./media/plus-icon.png)

6. **새 제외 규칙 만들기** 대화 상자에서 다음 매개 변수를 설정합니다.

    1. **Type rule name**(규칙 이름 입력) 아래에 규칙에 대한 설명이 포함된 이름을 지정합니다.
    **사용자 그룹 선택** 아래에서 Cloud App Security로 모니터링하지 않으려는 모든 그룹을 선택합니다.
    2. 이 규칙을 연결된 모든 앱에 적용할지 또는 **특정 앱**에만 적용할지 선택합니다. **특정 앱**을 선택하는 경우 Cloud App Security는 선택한 앱에 대해서만 선택한 그룹의 모니터링을 중지합니다. 즉, 그룹 **UI 팀 사용자** 및 **Active Directory**를 선택하면 Cloud App Security는 UI 팀 사용자가 수행한 Active Directory 활동을 제외한 모든 사용자 활동을 모니터링합니다.
    
       ![제외 규칙](./media/exclude-rule.png)

## <a name="example-results-for-include-and-exclude-rules"></a>포함 및 제외 규칙에 대한 예제 결과

만든 포함 및 제외 규칙은 함께 작동하여 Microsoft Cloud App Security가 수행하는 전체 모니터링 범위를 지정합니다. 다음은 만들 수 있는 포함 및 제외 규칙의 예와 이러한 규칙이 실행된 후 Microsoft Cloud App Security가 모니터링하는 내용의 최종 결과입니다.

다음 규칙을 만드는 경우:

- 사용자 그룹 “독일 모든 사용자” 제외
- 사용자 그룹 “글로벌 영업” Office 365 활동만 포함
- 사용자 그룹 “영업 관리자” Power BI 활동만 포함
- Salesforce가 Microsoft Cloud App Security에 연결되어 있고 이에 대한 규칙이 설정되어 있지 않습니다.

다음 사용자 활동이 모니터링됩니다.

|사용자|그룹 구성원|모니터링된 활동|
|----|----|----|
|Adriana|독일 모든 사용자<br>글로벌 영업<br>영업 관리자|없음|
|Alain|글로벌 영업|Office 365 및 모든 하위 앱(Power BI 제외)|
|Cornel|글로벌 영업<br>영업 관리자|Office 365 및 모든 하위 앱|
|Raymond|영업 관리자|Power BI만|

> [!NOTE] 
> 다른 앱은 이 규칙에서 그룹 범위 지정의 영향을 받지 않습니다.
> 이 예에서 Salesforce의 경우 모든 사용자 그룹에 대해 모든 활동이 모니터링됩니다.

## <a name="next-steps"></a>다음 단계  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
