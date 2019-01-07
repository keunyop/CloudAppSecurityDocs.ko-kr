---
title: 보안 구성 권장 사항 가져오기 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Azure Security Center와 통합하여 Cloud App Security에서 보안 구성 권장 사항을 가져오는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c6d8f8af-867b-43ab-adee-f06520577fe7
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 0cd5567c1f89375109a97be00c1053fe0da64833
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53175739"
---
# <a name="security-configuration"></a>보안 구성

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security는 Azure 환경에 대한 보안 구성 평가를 제공합니다. Azure Security Center에서 제공하는 평가는 누락된 구성과 보안 제어에 대한 권장 사항을 제공합니다.

## <a name="enable-security-configuration-recommendations"></a>보안 구성 권장 사항 사용

이 기능을 사용하려면 Azure AD 및 Azure Portal에서 적절한 권한이 필요합니다. 기본적으로 Azure AD 전역 관리자 역할은 Azure 구독에 대한 액세스를 제공하지 않습니다. 자신과 다른 사용자를 위한 Azure 구독에 대한 액세스 권한을 부여하려면 권한을 높입니다.

> [!IMPORTANT]
> 다음 프로세스를 완료한 후 권한 상승을 비활성화하는 것이 좋습니다.

Microsoft Cloud App Security에서 보안 구성 권장 사항을 활성화하려면:

1. <a href="https://docs.microsoft.com/azure/security-center/security-center-management-groups" target="_blank">Azure Security Center에 대한 테넌트 전체 가시성을 확보합니다</a>. 이 프로세스에는 다음이 포함됩니다.
   - 자신과 이 페이지에 대한 액세스 권한을 부여하려는 다른 Microsoft Cloud App Security 관리자에게 모든 구독에 대한 Reader의 역할을 부여합니다.
   - Azure Security Center에서 루트 관리 그룹에 역할 할당
   - Azure 구독에 대한 액세스 권한을 부여하기 위해 Azure AD 글로벌 관리자 권한을 상승합니다.
   - 문서에서는 보안 관리자가 되기 위한 프로세스를 설명합니다. 이 통합을 작동하기 위해 필요한 최소 권한은 **Reader**입니다.

2. 변경 내용을 적용할 <a href="https://ms.portal.azure.com/#blade/Microsoft_Azure_Security/SecurityMenuBlade/0" target="_blank">Azure Security Center</a>를 열어야 합니다.

3. Microsoft Cloud App Security 포털에서 **조사**, **보안 구성**으로 차례로 이동합니다. 
    - Microsoft Cloud App Security는 상위 50개 구독에 대한 권장 사항만을 제공합니다. 
    - 변경 내용을 적용하는 데 최대 15분이 걸릴 수 있습니다.

     ![보안 구성 메뉴](./media/security-configuration-menu.png)

4. 형식, 리소스 및 구독별로 권장 사항을 필터링할 수 있습니다. 또한 보안 구성 아이콘을 클릭할 수 있습니다. ![ASC 아이콘](./media/asc-icon.png) Azure Security Center의 권장 사항을 열고 권장 사항을 심층적으로 분석할 수 있습니다. 

보안 권장 사항을 구현하는 방법에 대한 자세한 내용은 [Azure Security Center에서 보안 권장 사항 관리](https://docs.microsoft.com/azure/security-center/security-center-recommendations)를 참조하세요.

   ![보안 구성](./media/security-configuration1.png)

## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
