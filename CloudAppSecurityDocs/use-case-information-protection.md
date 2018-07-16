---
title: Azure Information Protection 분류 레이블 자동 적용 | Microsoft Docs
description: 이 항목에서는 Microsoft Cloud App Security에서 Azure Information Protection 분류 레이블을 자동으로 적용하는 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b4d507b5fb3a646b31ba3c380b170c2abca18ddf
ms.sourcegitcommit: 3f02b02c294c4d7575702d9083ea3f94d3169ebc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38775891"
---
*적용 대상: Microsoft Cloud App Security*



# <a name="automatically-apply-azure-information-protection-classification-labels"></a>Azure Information Protection 분류 레이블 자동 적용  

이상적인 세계에서 모든 직원은 정보 보호의 중요성을 이해하고 정책을 준수하며 작업합니다. 그러나 현실 세계에서는 회계 업무를 수행하는 파트너가 잘못된 권한으로 Box 리포지토리에 문서를 업로드할 가능성이 높습니다. 그리고 한 주 후에 기업의 기밀 정보가 경쟁업체로 유출되었음을 알게 됩니다. 

Microsoft Cloud App Security는 이러한 종류의 재해를 사전에 방지할 수 있습니다.

Microsoft Cloud App Security는 Box 계정에 저장된 문서에 대한 공용 권한이 있는지와 분류 엔진을 통해 공개적으로 공유된 문서에 기밀 정보가 있는지를 식별합니다. 그리고 사용자에게 이 결과를 알리는 경고를 보내고, Azure Information Protection **기밀** 분류 레이블을 자동으로 적용하여 파일에 대한 추가 암호화를 제공합니다. 

>[!NOTE]
> - Azure Information Protection 레이블 적용은 사용 가능하고 긴 [거버넌스 작업](governance-actions.md) 목록 중 하나입니다.
> - 이 기능은 비즈니스용 Box, SharePoint 및 OneDrive에서 사용할 수 있습니다.

### <a name="enhanced-data-level-encryption-protection"></a>향상된 데이터 수준 암호화 보호

Cloud App Security와 Azure Information Protection을 통합하면 파일을 자동으로 암호화하여 보호 수준을 추가할 수 있습니다. 예를 들어 Azure Information Protection에서는 파일을 암호화하지만, Azure Information Protection을 지원하는 응용 프로그램(예: Office 365)은 파일을 열고 분류 레이블에 설정된 권한을 적용하는 방법을 인식하고 있습니다. 레이블을 사용하여 특정 보호 규칙을 적용할 수 있습니다. 예를 들어 파일을 열 수는 있지만 공유, 인쇄, 전달 또는 편집할 수 없도록 설정할 수 있습니다. 

이 강력한 보호 수준은 파일과 함께 이동합니다. 온라인 저장소 앱에 파일을 전송, 복사 및 저장하는 경우에도 파일이 계속 보호됩니다. 직원 중 한 명이 파일이 포함된 소형 드라이브를 분실하면 해당 파일이 잠기고 다른 사람이 이 파일을 열려고 하면 파일 소유자가 경고를 받게 됩니다. Cloud App Security를 사용하면 자동으로 보호를 적용할 수 있습니다. 예를 들어 신용 카드 번호가 있거나 재무 부서에서 업로드했고 외부에서 공유하는 모든 파일은 분류 레이블을 사용하여 자동으로 보호되도록 설정할 수 있습니다. 

## <a name="the-threat"></a>위협 
조직의 사용자는 기밀 고객 정보 파일을 Box에 저장하고, 조직의 모든 사용자와 공유하도록 설정합니다. 사용자는 직속 팀 뿐만 아니라 공급업체, 파트너 및 회사에 가끔 들르는 방문자를 비롯하여 전체 지원 직원이 해당 Box 계정에 액세스할 수 있음을 인식하지 못합니다. 조직의 Box 계정에 대한 액세스 권한이 있는 사람은 이제 해당 정보에 액세스할 수 있습니다. 조직에 위험할 뿐만 아니라 많은 국가에서 PII 규정을 위반하여 잠재적인 법적 문제가 발생할 수 있습니다.

## <a name="the-solution"></a>해결 방법
Azure Information Protection과 함께 Cloud App Security를 사용하여 데이터에 수반되는 영구 보호에 대한 분류 및 보호 정보가 포함되게 함으로써 저장 위치 또는 공유 대상에 관계 없이 해당 데이터를 보호된 상태로 유지합니다. 또한 이렇게 하면 동료뿐만 아니라 고객 및 파트너와도 안전하게 데이터를 공유할 수 있습니다. 공동 작업자 제거, 공유 기능 제거와 같이 Cloud App Security에서 지원하는 다른 [거버넌스 작업](governance-actions.md) 외에도, 사용자가 파일을 보거나 편집할 수는 있지만 인쇄하거나 전달할 수 없도록 하는 등 데이터에 액세스할 수 있는 사용자와 이 사용자가 수행할 수 있는 작업을 정의합니다.

## <a name="prerequisites"></a>필수 구성 요소

- 테넌트에서 [Cloud App Security 및 Azure Information Protection을 사용하도록 설정](azip-integration.md)합니다.
- Cloud App Security에 [Box를 연결](connect-box-to-microsoft-cloud-app-security.md)합니다.

## <a name="setting-up-data-protection"></a>데이터 보호 설정

Box 계정에 저장된 파일에서 신용 카드 번호를 검색하고, 해당 번호를 찾으면 Azure Information Protection 레이블을 자동으로 적용한 다음 해당 레이블이 있는 모든 파일에 발생하는 작업을 제어하는 정책을 설정하겠습니다.

1. Box에 저장된 중요한 데이터를 암호화하는 정책을 설정하여 Box에 저장하는 데이터 보호를 시작합니다.

    1. **컨트롤** 탭에서 [**Policies**](control-cloud-apps-with-policies.md)(정책)를 클릭합니다. 
    
    2. **정책 만들기**를 클릭하고 **파일 정책**을 선택합니다.
    
    3. *Box 데이터 보호* 정책을 호출합니다.
    
    4. **이 정책이 적용될 파일에 대한 필터 만들기** 아래에서 전용 및 중요 데이터를 대상으로 지정합니다.<br></br>
    예를 들어 Box에서 **부모 폴더**인 **고객 데이터**를 선택하고, **소유자**를 선택하고, 재무 팀을 선택합니다.
    
    4. 해당 폴더에서 신용 카드 정보가 포함되어 있는 파일을 찾습니다. **콘텐츠 검사 방법** 아래에서 **기본 제공 DLP**를 선택한 다음, **미리 설정된 식과 일치하는 파일 포함** 및 **모든 국가: 금융: 신용 카드 번호**를 선택합니다.
    
    5. **거버넌스** 아래에서 **Box** 섹션을 열고, **분류 레이블 적용**, 적용하려는 레이블을 차례로 선택합니다.
    
    6. [Cloud App Security가 Azure Information Protection과 통합되었기](azip-integration.md) 때문에 데이터를 보호하기 위해 사용할 분류 레이블을 기존 분류 레이블 목록에서 선택할 수 있습니다.
 
    7. **만들기**를 클릭합니다. 
   
   ![정책에 분류 레이블 추가](./media/aip-auto-policy.png)
     
2. 일치 항목 조사
    
    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동해 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하여 파일 서랍을 열어서 일치를 조사할 수 있습니다. 서랍에서 이 파일이 일치하는 다른 정책을 확인할 수 있습니다. 
     
## <a name="validating-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 Box 계정으로 이동하고 **Customer data**(고객 데이터) 폴더의 파일에 액세스를 시도합니다.
3. 정책 보고서로 이동합니다. 파일 정책 일치 항목이 곧 표시됩니다. 
4. 일치 항목을 클릭하여 보호된 파일을 확인할 수 있습니다. 일치 항목 자체는 중요한 데이터를 보호하기 위해 마스킹됩니다. 

>[!NOTE]
> - Cloud App Security는 현재 비즈니스용 Box, SharePoint 및 OneDrive에서 Azure Information Protection 레이블을 자동으로 적용할 수 있도록 지원합니다.
> - Cloud App Security를 사용하여 문서에 레이블을 지정하면 시각적 표시가 즉시 적용되지는 않지만 해당 문서를 Office 응용프로그램에서 열고 문서를 처음 저장할 때 적용됩니다. 자세한 내용은 [Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-markings#when-visual-markings-are-applied)의 시각적 표시에 레이블을 구성하는 방법을 참조하세요.

 ## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  