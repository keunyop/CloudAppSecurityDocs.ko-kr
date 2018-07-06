---
title: Cloud App Security에서 보안 구성 권장 사항 가져오기 | Microsoft Docs
description: 이 문서에서는 Azure Security Center와 통합하여 Cloud App Security에서 보안 구성 권장 사항을 가져오는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/27/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c6d8f8af-867b-43ab-adee-f06520577fe7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0d21df4cac9ca31207b94061d5bb18ec857668ac
ms.sourcegitcommit: c7e4351345d55cfeb0517651446490ce5f208651
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2018
ms.locfileid: "37140774"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="security-configuration"></a>보안 구성

Microsoft Cloud App Security는 Azure 환경의 보안 구성 평가를 제공하고, Azure Security Center에서 제공하는 누락된 구성 및 보안 제어에 대한 권장 사항을 제공합니다. 

이 기능을 사용하려면 Azure AD 및 Azure Portal에서 적절한 권한을 보유해야 합니다.
 
기본적으로 Azure AD 전역 관리자 역할은 Azure 구독에 대한 액세스를 제공하지 않습니다. 이로 인해 자신 및 다른 사용자에게 Azure 구독에 대한 액세스를 부여할 수 있도록 권한을 상승시켜야 합니다. 

> [!NOTE]
> 다음 프로세스를 완료한 후 권한 상승을 비활성화하는 것이 좋습니다.

Microsoft Cloud App Security에서 보안 구성 권장 사항을 활성화하려면:

1. 자신 및 이 페이지에 대한 액세스 권한을 부여하려는 다른 모든 Microsoft Cloud App Security 관리자에게 모든 구독에 대한 독자 역할을 부여하고, Azure Security Center에서 루트 관리 그룹의 역할을 할당하고, Azure 구독에 대한 액세스 권한을 부여하도록 Azure AD 전역 관리자의 권한을 상승시켜 <a href="https://docs.microsoft.com/azure/security-center/security-center-management-groups" target="_blank">Azure Security Center에 대한 테넌트 수준 가시성을 확보</a>합니다. 

   > [!NOTE]
   > 문서에서는 보안 관리자가 되기 위한 프로세스를 설명합니다. 이 통합을 작동하기 위해 필요한 최소 권한은 독자입니다.

2. 변경 내용을 적용할 <a href="https://ms.portal.azure.com/#blade/Microsoft_Azure_Security/SecurityMenuBlade/0" target="_blank">Azure Security Center</a>를 열어야 합니다.

3. Microsoft Cloud App Security 포털에서 **조사**, **보안 구성**으로 차례로 이동합니다. 

   ![보안 구성 메뉴](./media/security-configuration-menu.png)

   > [!NOTE]
   > Microsoft Cloud App Security는 상위 50개 구독에 대한 권장 사항만을 제공합니다.
   > 변경 내용을 적용하는 데 최대 15분이 걸릴 수 있습니다.

5. 형식, 리소스 및 구독별로 권장 사항을 필터링할 수 있습니다. 또한 보안 구성 아이콘 ![ASC 아이콘](./media/asc-icon.png)을 클릭하여 자세한 내용을 위해 Azure Security Center의 권장 사항을 열고 권장 사항을 심층적으로 분석할 수 있습니다. <br></br><br></br>보안 권장 사항을 구현하는 방법에 대한 자세한 내용은 [Azure Security Center에서 보안 권장 사항 관리](https://docs.microsoft.com/azure/security-center/security-center-recommendations)를 참조하세요.

 
   ![보안 구성](./media/security-configuration1.png)

 

## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
