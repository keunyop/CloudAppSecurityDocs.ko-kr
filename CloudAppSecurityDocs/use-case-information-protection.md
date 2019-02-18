---
title: Azure Information Protection 분류 레이블 자동 적용
description: 이 자습서에서는 Microsoft Cloud App Security에서 Azure Information Protection 분류 레이블을 자동으로 적용하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 1/27/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 9da835fc1f1a9c3fc85035d83a0b2e8415ebc337
ms.sourcegitcommit: 8ef0438fa35916c48625ff750cb85e9628d202f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56281851"
---
# <a name="tutorial-automatically-apply-azure-information-protection-classification-labels"></a>자습서: Azure Information Protection 분류 레이블 자동 적용

*적용 대상: Microsoft Cloud App Security*

이상적인 세계에서 모든 직원은 정보 보호의 중요성을 이해하고 정책을 준수하며 작업합니다. 하지만 실제로는 계정을 가진 파트너가 잘못된 사용 권한으로 Box 리포지토리에 문서를 업로드할 가능성이 높습니다. 한 주 후에 기업의 기밀 정보가 경쟁사에게 유출되었음을 알게되었습니다. Microsoft Cloud App Security는 이러한 종류의 재해를 사전에 방지할 수 있습니다. 이 기능은 비즈니스용 Box, SharePoint 및 OneDrive에서 사용할 수 있습니다. Azure Information Protection 레이블 적용은 사용 가능하고 긴 [거버넌스 작업](governance-actions.md) 목록 중 하나입니다.

이 자습서는 클라우드 스토리지에 저장된 문서에 설정된 공용 권한을 식별하도록 지원하므로 위반 발생 시 경고가 표시됩니다. 또한 Azure Information Protection **기밀** 분류 레이블을 자동으로 적용하여 파일에 추가 암호화를 제공할 수 있습니다.

> [!div class="checklist"]
> * 데이터 보호 설정 
> * 정책 유효성 검사


## <a name="enhanced-data-level-encryption-protection"></a>향상된 데이터 수준 암호화 보호

Cloud App Security와 Azure Information Protection을 통합하면 파일을 자동으로 암호화하여 보호 수준을 추가할 수 있습니다. Azure Information Protection이 파일을 암호화하면 Azure Information Protection을 지원하는 애플리케이션(예: Office 365)은 파일을 열고 분류 레이블에 설정된 사용 권한을 적용하는 방법을 인식합니다. 레이블을 사용하여 특정 보호 규칙을 적용합니다. 예를 들어 파일을 열 수는 있지만 공유, 인쇄, 전달 또는 편집할 수 없도록 설정합니다.

이 강력한 보호 수준은 파일에 계속 설정됩니다. 파일을 보내거나, 복사하거나, 온라인 스토리지 앱에 저장하는 경우에도 파일은 계속 보호됩니다. 한 명의 직원이 파일이 있는 thumb 드라이브를 손실한 경우 파일이 잠깁니다. 누군가 파일을 열려고 하는 경우 파일 소유자는 경고를 받게 됩니다. Cloud App Security를 사용하면 자동으로 보호를 적용할 수 있습니다. 예를 들어 신용 카드 번호가 있거나 재무 부서에서 업로드했고 외부에서 공유된 모든 파일은 분류 레이블을 사용하여 자동으로 보호되도록 설정합니다.

## <a name="the-threat"></a>위협

조직의 사용자는 기밀 고객 정보 파일을 Box에 저장하고, 조직의 모든 사용자와 공유하도록 설정합니다. 사용자는 직속 팀뿐만 아니라 전체 지원팀 직원에게 해당 Box 계정에 대한 액세스 권한이 있는지 인식하지 못합니다. 이 액세스 권한에는 공급 업체, 파트너 및 사무실에 드나드는 방문자가 포함됩니다. 조직의 Box 계정에 대한 액세스 권한이 있는 사람은 이제 해당 정보에 액세스할 수 있습니다. 해당 액세스는 조직에 위험할 뿐만 아니라 많은 국가에서 개인 정보 규정을 위반하여 잠재적인 법적 문제가 발생할 수 있습니다.

## <a name="the-solution"></a>해결 방법

Azure Information Protection과 함께 Cloud App Security를 사용하여 데이터에 수반되는 영구 보호에 대한 분류 및 보호 정보가 포함되게 함으로써 저장 위치 또는 공유 대상에 관계 없이 해당 데이터를 보호합니다. 이 보호를 사용하면 동료, 고객 및 파트너와도 안전하게 데이터를 공유할 수 있습니다. 데이터에 액세스할 수 있는 사용자 및 수행할 수 있는 내용을 정의합니다. 예를 들어, 사용자가 파일을 보고 편집할 수 있지만 인쇄하거나 전달할 수 없게 합니다. 제거 협력자 및 제거 공유 기능 등 Cloud App Security에서 파일에 지원되는 다른 [거버넌스 작업](governance-actions.md)을 추가할 수도 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

- 테넌트에서 [Cloud App Security 및 Azure Information Protection을 사용하도록 설정](azip-integration.md)합니다.
- Cloud App Security에 [Box를 연결](connect-box-to-microsoft-cloud-app-security.md)합니다.

## <a name="set-up-data-protection"></a>데이터 보호 설정

Box 계정에 저장된 파일에서 신용 카드 번호를 찾는 정책을 설정해 보겠습니다. 파일이 있는 경우 자동으로 Azure Information Protection 레이블을 적용하고 해당 레이블이 있는 모든 파일에 발생한 결과를 제어합니다.

1. Box에 저장된 중요한 데이터를 암호화하는 정책을 설정하여 Box에 저장하는 데이터 보호를 시작합니다.

    1. **컨트롤** 탭에서 [**Policies**](control-cloud-apps-with-policies.md)(정책)를 클릭합니다. 

    2. **정책 만들기**를 클릭하고 **파일 정책**을 선택합니다.

    3. *Box 데이터 보호* 정책을 호출합니다.

    4. **이 정책이 적용될 파일에 대한 필터 만들기** 아래에서 전용 및 중요 데이터를 대상으로 지정합니다.
        - 예를 들어 Box에서 **부모 폴더**인 **고객 데이터**를 선택하고, **소유자**인 재무 팀을 선택합니다.

    5. 해당 폴더 내에서 신용 카드 정보가 포함된 파일을 찾습니다. **콘텐츠 검사 방법** 아래에서 **기본 제공 DLP**를 선택하고, **미리 설정된 식과 일치하는 파일 포함** 및 **모든 국가: 금융: 신용 카드 번호**를 선택합니다.

    6. **거버넌스** 아래에서 **Box** 섹션을 열고, **분류 레이블 적용**을 선택합니다. 적용하려는 레이블을 선택합니다.

    7. [Cloud App Security가 Azure Information Protection과 통합되었기](azip-integration.md) 때문에 데이터를 보호하기 위해 사용할 분류 레이블을 기존 분류 레이블 목록에서 선택할 수 있습니다.

    8. **만들기**를 클릭합니다. 

   ![정책에 분류 레이블 추가](./media/aip-auto-policy.png)

2. 일치 항목 조사

    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동합니다. 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하여 파일 서랍을 열어서 일치를 조사할 수 있습니다. 서랍에서 이 파일이 일치하는 다른 정책을 확인할 수 있습니다.

## <a name="validate-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 Box 계정으로 이동하고 **Customer data** 폴더의 파일에 액세스를 시도합니다.
2. 정책 보고서로 이동합니다. 파일 정책 일치 항목이 곧 표시됩니다. 
3. 일치 항목을 클릭하여 보호된 파일을 확인할 수 있습니다. 일치 항목 자체는 중요한 데이터를 보호하기 위해 마스킹됩니다.

>[!NOTE]
>
> - Cloud App Security는 현재 비즈니스용 Box, SharePoint 및 OneDrive에서 Azure Information Protection 레이블을 자동으로 적용할 수 있도록 지원합니다.
> - Cloud App Security를 사용하여 문서에 레이블을 지정하면 시각적 표시가 즉시 적용되지는 않지만 해당 문서를 Office 응용프로그램에서 열고 문서를 처음 저장할 때 적용됩니다. 자세한 내용은 [Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-markings#when-visual-markings-are-applied)의 시각적 표시에 레이블을 구성하는 방법을 참조하세요.

## <a name="next-steps"></a>다음 단계

[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
