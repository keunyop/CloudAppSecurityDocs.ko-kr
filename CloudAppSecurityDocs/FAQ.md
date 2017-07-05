---
title: "Cloud App Security에 대한 질문과 대답 | Microsoft 문서"
description: "이 문서에서는 Cloud App Security에 대한 질문과 대답을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 3e0c14d142f9154b5e986105899c9445667518c6
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2017
---
# <a name="frequently-asked-questions"></a>질문과 대답

## <a name="what-kind-of-permissions-do-i-need-to-have-in-order-to-access-cloud-app-security"></a>Cloud App Security에 액세스하려면 어떤 종류의 사용 권한이 있어야 하나요?

Azure Active Directory에서 전역 관리자, 준수 관리자 또는 보안 관리자여야 합니다. Office 365 보안 및 준수 센터에서 이러한 역할을 가지는 것으로는 충분하지 않습니다.
사용자를 Azure Active Directory에서 전역 관리자, 준수 관리자 또는 보안 관리자로 설정하려면 Windows PowerShell에서 다음을 실행합니다.

        $cred = Get-Credential
        Connect-MsolService -credential $cred
        Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
 OR Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress “XX@XX.XX”

## <a name="see-also"></a>참고 항목  
정책을 사용 및 설정하여 클라우드 응용 프로그램의 사용을 제어하는 방법을 알아보려면 [정책을 사용하여 클라우드 응용 프로그램 제어](control-cloud-apps-with-policies.md)를 참조하세요.   
기술 지원을 받으려면 [Cloud App Security 보조 지원](http://support.microsoft.com/oas/default.aspx?prid=16031) 페이지를 방문하세요.   
프리미어 고객은 [프리미어 포털](https://premier.microsoft.com/)에서 직접 Cloud App Security를 선택할 수도 있습니다.  
