---
title: Microsoft 데이터 분류 서비스를 사용하여 Cloud App Security 콘텐츠 검사
description: 이 문서에서는 Microsoft 데이터 분류 서비스를 사용하여 DLP 콘텐츠 검사를 수행할 때 Cloud App Security에서 수행하는 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: bf25d1e6-e5dc-449f-b50e-1cd4a21b6d3d
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: d060980768426cbabe0f3c7cb976aadf88037b7d
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53174991"
---
# <a name="microsoft-data-classification-services-integration"></a>Microsoft 데이터 분류 서비스 통합

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security를 통해 기본적으로 Microsoft 데이터 분류 서비스를 사용하여 클라우드 앱의 파일을 분류할 수 있습니다. Microsoft 데이터 분류 서비스는 Office 365, Azure Information Protection 및 Microsoft Cloud App Security에서 통합 정보 보호 환경을 제공합니다. 분류 서비스를 통해 훨씬 더 많은 앱에서 이미 내린 결정을 사용하여 데이터 분류 작업을 Microsoft Cloud App Security로 보호되는 타사 클라우드 앱으로 확장할 수 있습니다.

>[!NOTE]
> 이 기능은 현재 미국, 유럽(프랑스 제외) 및 APAC에서 사용할 수 있습니다.


## <a name="enable-content-inspection-with-data-classification-services"></a>데이터 분류 서비스를 통한 콘텐츠 검사 사용

추가 구성 없이 **Microsoft 데이터 분류 서비스**를 사용하도록 **검사 방법**을 설정할 수 있는 옵션이 있습니다. 이 옵션은 Microsoft Cloud App Security에서 파일에 대한 데이터 유출 방지 정책을 만들 때 유용합니다.


1. [파일 정책](data-protection-policies.md) 페이지의 **검사 방법**에서 **데이터 분류 서비스**를 선택합니다.
     ![데이터 분류 서비스 설정](./media/dcs-enable.png)
2. **임의** 조건 또는 **모든** 조건을 충족할 때 정책을 적용해야 하는지를 선택합니다.
3. **중요한 정보 유형**을 선택하여 **검사 유형을 선택**합니다.
 ![데이터 분류 서비스 설정](./media/dcs-sensitive-information-type.png)

4. [기본 중요 정보 유형](https://support.office.com/article/what-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b)을 사용하여 Microsoft Cloud App Security로 보호되는 파일에 어떤 일이 발생하는지 정의할 수 있습니다. [Office 365 사용자 지정 중요 정보 유형](https://support.office.com/article/create-a-custom-sensitive-information-type-82c382a5-b6db-44fd-995d-b333b3c7fc30)을 모두 다시 사용할 수도 있습니다.

5. 필요에 따라 일치하는 항목의 마지막 4자를 마스크 해제할 수 있습니다. 기본적으로 일치하는 항목은 마스킹되고 컨텍스트에 표시되며 일치하는 항목 앞뒤의 40자를 포함합니다. 이 확인란을 선택하면 일치하는 항목 자체의 마지막 4자가 마스크 해제됩니다.

6. 정책에 대한 경고 및 거버넌스 작업을 설정할 수도 있습니다. 자세한 내용은 [파일 정책](data-protection-policies.md) 및 [거버넌스 작업](governance-actions.md)을 참조하세요.

이러한 정책을 설정하면 Office 365 DLP 기능의 이점을 다른 모든 사용 권한 클라우드 앱으로 쉽게 확장하고 Microsoft Cloud App Security에서 제공하는 전체 도구 집합(예: [자동으로 Azure Information Protection 분류 레이블을 적용](azip-integration.md)하는 기능 및 공유 권한을 제어하는 기능)을 사용하여 앱에 저장된 데이터를 보호할 수 있습니다.



## <a name="next-steps"></a>다음 단계  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  