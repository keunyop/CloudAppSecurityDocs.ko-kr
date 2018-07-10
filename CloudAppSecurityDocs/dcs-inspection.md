---
title: Cloud App Security에서 Microsoft 데이터 분류 서비스를 사용하여 콘텐츠 검사를 수행하는 방법 | Microsoft Docs
description: 이 문서에서는 Microsoft 데이터 분류 서비스를 사용하여 DLP 콘텐츠 검사를 수행할 때 Cloud App Security에서 수행하는 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/1/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: bf25d1e6-e5dc-449f-b50e-1cd4a21b6d3d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a1a9455681106c066888cf29c83971914e35babb
ms.sourcegitcommit: 9d2a34a2d4145b39d855dd6f596c0fc858b92f9b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37340008"
---
*적용 대상: Microsoft Cloud App Security*



# <a name="microsoft-data-classification-services-integration"></a>Microsoft 데이터 분류 서비스 통합

Microsoft Cloud App Security를 통해 기본적으로 Microsoft 데이터 분류 서비스를 활용하여 클라우드 앱의 파일을 분류할 수 있습니다.
Microsoft 데이터 분류 서비스는 Office 365, Azure Information Protection 및 Microsoft Cloud App Security에서 통합 정보 보호 환경을 제공하며, 데이터 분류 작업을 Microsoft Cloud App Security로 보호되는 타사 클라우드 앱으로 확장할 수 있도록 하여 이미 한 결정을 훨씬 더 많은 수의 앱에서 활용할 수 있게 해줍니다.

>[!NOTE]
> 이 기능은 현재 미국과 유럽(프랑스 제외)에서만 사용할 수 있는 기능입니다.

추가 구성이 필요하지 않으며 Microsoft Cloud App Security에서 파일에 대한 데이터 손실 방지 정책을 만들 때 자동으로 **Microsoft 데이터 분류 서비스**를 사용하도록 **검사 방법**을 설정하는 옵션이 제공됩니다.

![데이터 분류 서비스 설정](./media/dcs-enable.png)

데이터 분류 서비스를 통한 콘텐츠 검사를 사용하도록 설정하려면:

1. [파일 정책](data-protection-policies.md) 페이지의 **검사 방법**에서 **데이터 분류 서비스**를 선택합니다.
2. **임의** 조건 또는 **모든** 조건을 충족할 때 정책을 적용해야 하는지를 선택합니다.
3. 중요한 정보 유형을 선택하여 콘텐츠 검사 유형을 선택합니다.
 ![데이터 분류 서비스 설정](./media/dcs-sensitive-information-type.png)

5. [기본 중요한 정보 유형](https://support.office.com/article/what-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b) 및 Office 365에서 만든 [사용자 지정 중요한 정보 유형](https://support.office.com/article/create-a-custom-sensitive-information-type-82c382a5-b6db-44fd-995d-b333b3c7fc30)(Regex, 키워드 및 큰 사전이 포함된 복잡한 패턴을 지원함)을 사용하고 이를 재사용하여 Microsoft Cloud App Security로 보호되는 파일에 발생하는 상황을 정의할 수 있습니다.

6. 필요에 따라 일치하는 항목의 마지막 4자를 마스크 해제할 수 있습니다. 기본적으로 일치하는 항목은 마스킹되고 컨텍스트에 표시되며 일치하는 항목 앞뒤의 40자를 포함합니다. 이 확인란을 선택하면 일치하는 항목 자체의 마지막 4자가 마스크 해제됩니다.

7. 정책에 대한 경고 및 거버넌스 작업을 설정할 수도 있습니다. 자세한 내용은 [파일 정책](data-protection-policies.md) 및 [거버넌스 작업](governance-actions.md)을 참조하세요.

Microsoft Cloud App Security에서 이러한 정책을 설정하면 손쉽게 Office 365 DLP 기능의 이점을 다른 모든 사용 권한 클라우드 앱으로 확장하고 Microsoft Cloud App Security에서 제공하는 전체 도구 집합(예: [자동으로 Azure Information Protection 분류 레이블을 적용](azip-integration.md)하는 기능 및 공유 권한을 제어하는 기능)을 사용하여 해당 앱에 저장된 데이터를 보호할 수 있습니다.



## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  