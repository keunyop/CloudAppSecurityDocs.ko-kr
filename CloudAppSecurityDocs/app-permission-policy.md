---
title: Cloud App Security에서 앱 사용 권한을 제어하는 정책 만들기 | Microsoft Docs
description: 이 항목에서는 Microsoft Cloud App Security에서 앱 사용 권한 정책을 만들고 사용하는 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/24/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9f68302c-bb3d-450c-bbf5-f8130cb163e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 02af6d6c109812156f8b8a3cf38a6f0599f2fec4
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143159"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="app-permission-policies"></a>앱 사용 권한 정책

환경에 연결된 [OAuth 앱의 기존 조사](manage-app-permissions.md) 외에도 OAuth 앱이 특정 기준을 충족하는 경우 자동화된 알림을 받을 수 있도록 사용 권한 정책을 설정할 수 있습니다. 예를 들어 높은 사용 권한 수준이 필요하고 50명을 초과하는 사용자에 의해 권한이 부여된 앱이 있는 경우 자동으로 경고를 받을 수 있습니다. 

앱 사용 권한 정책을 사용하면 Office 365, G Suite 및 Salesforce에 대해 각 앱이 요청한 사용 권한 및 권한이 부여된 사용자를 조사할 수 있습니다. 이러한 사용 권한을 승인됨 또는 금지됨으로 표시할 수도 있습니다. 금지됨으로 표시하면 권한을 부여한 사용자의 앱에 대한 사용 권한을 철회합니다. 

새로운 앱 사용 권한 정책을 만들려면:
1. **조사**에서 **앱 사용 권한**을 선택합니다.
2. 필요에 따라 앱을 필터링합니다. 예를 들어 **사용 권한**을 요청한 모든 앱을 보고 **사서함에서 일정을 수정**할 수 있습니다.
3. **검색을 통한 새 정책** 단추를 클릭합니다. 
    ![검색을 통한 새 정책](./media/app-permissions-filter.png)
4. **커뮤니티 사용량** 필터를 사용하여 이 앱에 대해 허용된 사용 권한이 일반적인지, 일반적이지 않은지, 아니면 드문지에 대한 정보를 가져옵니다. 드물지만 높은 심각도 수준의 사용 권한을 요청하거나 많은 사용자의 사용 권한을 요청하는 앱이 있는 경우에 유용할 수 있습니다. 

또는 **제어** 뒤에 **정책**을 클릭하여 정책을 만들 수 있습니다. 그런 다음, **정책 만들기** 뒤에 **앱 사용 권한 정책**을 클릭합니다.

  
   ![새로운 앱 사용 권한 정책](./media/app-permissions-policy.png)



  ## <a name="see-also"></a>참고 항목  
  [데이터 보호 정책](data-protection-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  