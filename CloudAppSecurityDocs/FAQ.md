---
title: 질문과 대답 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud App Security에 대한 질문과 대답을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 53477b78350b2377e71780769cf50c1df48bcbdf
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53176674"
---
# <a name="frequently-asked-questions"></a>질문과 대답

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 Cloud App Security에 대한 질문과 대답을 제공합니다.

## <a name="what-kind-of-permissions-do-i-need-to-access-cloud-app-security"></a>Cloud App Security에 액세스하려면 어떤 종류의 사용 권한이 있어야 하나요?

Azure Active Directory에서 글로벌 관리자, 준수 관리자 또는 보안 관리자여야 합니다. Office 365 보안 및 규정 준수 센터에서 이러한 역할을 수행하는 것만으로는 충분하지 않습니다. PowerShell을 사용하여 사용자를 Azure Active Directory에서 글로벌 관리자, 준수 관리자 또는 보안 관리자로 설정할 수 있습니다. 아래의 cmdlet을 실행합니다.

```powershell

 $cred = Get-Credential
 Connect-MsolService -credential $cred
 Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
```

 또는

```powershell
 Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress “XX@XX.XX”
```

## <a name="next-steps"></a>다음 단계  
클라우드 앱 사용을 제어하기 위한 정책을 설정하고 사용하는 방법을 알아보려면 [정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)를 참조하세요.   

프리미어 고객은 [프리미어 포털](https://premier.microsoft.com/)에서 직접 Cloud App Security를 선택할 수도 있습니다.  
