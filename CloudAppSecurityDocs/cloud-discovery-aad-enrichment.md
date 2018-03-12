---
title: "Azure AD 사용자 이름을 사용하여 Cloud App Security Discovery 데이터 보강 | Microsoft Docs"
description: "이 문서에서는 Azure AD 사용자 이름을 사용하여 Cloud App Security Discovery 데이터를 보강하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/3/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 45295c2c-3e4d-4482-bf95-2e47072f9236
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 88bc530ec33f03da650dba558123ac1e0c217183
ms.sourcegitcommit: 9de7ed2224aeed049fc2a87e52307988f8837eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="cloud-discovery-enrichment"></a>Cloud Discovery 보강

Azure Active Directory 사용자 이름 데이터를 사용하여 Cloud Discovery 데이터를 보강할 수 있습니다. 이 기능을 사용하도록 설정하면 검색 트래픽 로그에 받은 사용자 이름이 Azure AD 사용자 이름과 일치하고 이 사용자 이름으로 대체되어 다음과 같은 새 기능을 사용할 수 있습니다.
-   Azure Active Directory 사용자에 의한 섀도 IT 사용량을 조사할 수 있습니다.
-   검색된 클라우드 앱 사용을 API로 수집된 활동과 상호 연결할 수 있습니다.
-   Azure AD 사용자 그룹을 기반으로 사용자 지정 로그를 만들 수 있습니다. 예를 들어 특정 마케팅 부서에 대한 섀도 IT 보고서를 만들 수 있습니다.


## <a name="prerequisites"></a>필수 구성 요소:
- 데이터 원본은 사용자 이름 정보를 제공해야 합니다.
- Office 365 앱 커넥터가 연결되어야 합니다.

## <a name="enabling-user-data-enrichment"></a>사용자 데이터 보강 사용 
    
1. [설정] 코그 아래에서 **Cloud Discovery 설정**을 선택합니다.
     
2. Cloud App Security에서 Azure Active Directory 데이터를 사용하여 기본적으로 사용자 이름을 보강할 수 있도록 하려면, **사용자 보강** 탭에서 **Azure Active Directory 사용자 이름으로 검색된 사용자 ID를 보강하세요.**를 선택합니다.

3. **Save**을 클릭합니다.
 
![Azure AD 사용자 이름을 사용하여 Cloud App Security Discovery 보강](./media/discovery-enrichment.png)
  

  
      
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
    
      
  