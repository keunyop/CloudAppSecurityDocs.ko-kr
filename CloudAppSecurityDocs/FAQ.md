---
title: "Cloud App Security에 대한 질문과 대답 | Microsoft 문서"
description: "이 문서에서는 Cloud App Security에 대한 질문과 대답을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 92ad2a378b0ab0f127ef22c9746f2957f43576a8
ms.sourcegitcommit: 355226ee21981563066d637e7db0bff0d53c2da6
translationtype: HT
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
