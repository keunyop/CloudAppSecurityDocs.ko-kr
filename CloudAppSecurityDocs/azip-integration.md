---
title: Cloud App Security와 Azure Information Protection 통합
description: 이 문서에서는 Cloud App Security에서 Azure Information Protection 태그를 활용하여 조직의 클라우드 응용 프로그램 사용을 상세히 제어하는 방법에 관한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: bbe1bd310f7c661ba631f088a474baf536fb8d32
ms.sourcegitcommit: 9f322632666636de12ac332349130d7961dbbb81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2019
ms.locfileid: "54059450"
---
# <a name="azure-information-protection-integration"></a>Azure Information Protection 통합

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security를 통해 Azure Information Protection 분류 레이블을 보호 여부와 상관없이 파일 정책 거버넌스 작업으로 파일에 자동 적용할 수 있습니다. Cloud App Security 포털 내에서 적용된 분류 레이블을 필터링하여 파일을 조사할 수도 있습니다. 분류를 사용하면 클라우드에서 중요한 데이터를 더 잘 볼 수 있고 제어할 수 있습니다. Azure Information Protection을 Cloud App Security와 통합하는 작업은 확인란 하나를 선택하는 것만큼 쉽습니다. 

> [!NOTE]
> [Office 365 보안 및 규정 준수 센터에 대한 분류 레이블을 마이그레이션](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)한 경우, 이 문서는 Microsoft Information Protection 통합 레이블과도 관련이 있습니다. 기존 분류 레이블을 마이그레이션하지 않고 Office 365 보안 및 규정 준수 센터에서 새 레이블을 만들기 시작하면 Cloud App Security는 Azure Information Protection 포털에 구성된 기존 레이블만 사용합니다.


Azure Information Protection을 Cloud App Security에 통합하여 다음과 같이 클라우드에서 서비스와 안전한 파일의 전체 성능을 모두 사용할 수 있습니다.
- 특정 정책과 일치하는 파일에 분류 레이블을 거버넌스 작업으로 적용할 수 있는 기능
- 중앙 위치에서 분류된 모든 파일을 보는 기능
- 분류 수준에 따라 조사하고 클라우드 애플리케이션을 통해 중요한 데이터의 노출을 수량화하는 기능
- 분류된 파일이 적절하게 처리되도록 하는 정책을 만드는 기능


> [!NOTE] 
> 이 기능을 사용하도록 설정하려면 Cloud App Security 라이선스와 Azure Information Protection Premium P1 라이선스가 모두 필요합니다. 두 라이선스가 모두 있으면 Cloud App Security는 즉시 Azure Information Protection 서비스에서 조직 레이블을 동기화합니다.


## <a name="prerequisites"></a>필수 구성 요소

- Azure Information Protection 통합 작업을 하려면 [Office 365용 앱 커넥터](connect-office-365-to-microsoft-cloud-app-security.md)를 사용하도록 설정해야 합니다.

Cloud App Security는 현재 다음 파일 형식에 Azure Information Protection 분류 레이블을 적용하도록 지원합니다.

- Word: docm, docx, dotm, dotx
- Excel: xlam, xlsm, xlsx, xltx
- PowerPoint: potm, potx, ppsx, ppsm, pptm, pptx
- 이후 버전에서 PDF를 사용할 수 있습니다. 

이 기능은 현재 Box, G Suite, SharePoint Online 및 비즈니스용 OneDrive에 저장된 파일에서 사용할 수 있습니다. 향후 버전에서는 더 많은 클라우드 앱이 지원됩니다.

Cloud App Security 외부에서 보호 레이블이 지정된 파일은 현재 Cloud App Security에서 검사하거나 변경할 수 없습니다. Cloud App Security 외부로 레이블이 지정된(보호되지 않은) 파일은 검사가 가능하며 Cloud App Security에서 Cloud App Security 정책에 정의된 대로 다른 레이블(보호 여부와 상관없이)을 적용할 수 있습니다.


## <a name="how-it-works"></a>작동 방식
사용자는 [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)의 파일 분류 레이블에 익숙할 것입니다. Cloud App Security에서 Azure Information Protection 분류 태그를 볼 수 있습니다. Cloud App Security를 Azure Information Protection과 통합하는 즉시 Cloud App Security는 다음과 같이 파일을 검색합니다.

1. Cloud App Security는 테넌트에서 사용되는 모든 분류 레이블의 목록을 검색합니다. 이 작업은 목록을 최신 상태로 유지하기 위해 매시간 수행됩니다.

2. 그런 다음 Cloud App Security는 다음과 같이 분류 레이블에 대해 파일을 검색합니다.

    - 자동 검색을 활성화한 경우 새로운 파일 또는 수정된 파일이 검색 큐에 모두 추가되고 기존 파일 및 리포지토리는 모두 검색, 분류 및 보호됩니다.
     -  분류 레이블을 검색하도록 파일 정책을 설정한 경우 이러한 파일이 분류 레이블에 대한 검색 큐에 추가됩니다.

3. 위에서 언급했듯이 이러한 검색은 Cloud App Security가 테넌트에서 사용되는 분류 레이블을 확인하기 위해 수행하는 초기 검색에서 발견된 분류 레이블에 대한 것입니다. 테넌트 외부에 있는 사람이 설정한 분류 레이블인 외부 레이블이 분류 레이블 목록에 추가됩니다. 이러한 항목에 대해 검색하지 않으려면 **Only scan files for Azure Information Protection classification labels from this tenant**(이 테넌트의 Azure Information Protection 분류 레이블에 대한 파일만 검색) 확인란을 선택합니다.

4. Cloud App Security에 대해 Azure Information Protection을 사용하도록 설정하고 나면 Office 365에 추가되는 모든 새 파일도 분류 레이블에 대해 검색됩니다.

5. 분류 레이블을 자동으로 적용하는 Cloud App Security 내에서 새 정책을 만들 수 있습니다.

## <a name="how-to-integrate-azure-information-protection-with-cloud-app-security"></a>Cloud App Security와 Azure Information Protection을 통합하는 방법
  
### <a name="enable-azure-information-protection"></a>Azure Information Protection 사용

확인란 하나를 클릭하기만 하면 Azure Information Protection을 Cloud App Security와 통합할 수 있습니다. 자동 검색을 사용하면 정책을 만들 필요 없이 Office 365 파일에서 Azure Information Protection 분류 레이블을 검색할 수 있습니다. 이 기능을 사용하도록 설정한 후, 클라우드 환경에 Azure Information Protection 분류 레이블로 레이블이 지정된 파일이 있는 경우 해당 파일이 Cloud App Security에 표시됩니다.

Cloud App Security를 사용하도록 설정하여 분류 레이블에 대해 사용하도록 설정된 콘텐츠 검사로 파일을 검색하려면:

1. Cloud App Security의 설정 코그에서 **시스템** 제목 아래 **설정** 페이지를 선택합니다.
    ![설정 메뉴](./media/azip-system-settings.png)
1. **Azure Information Protection**에서 **파일에서 자동으로 Azure Information Protection 분류 레이블 검색**을 선택합니다. 
    ![azure information protection 사용](./media/enable-azip.png)

Azure Information Protection을 사용하도록 설정하고 나면 Cloud App Security에서 분류 레이블이 있는 파일을 보고 레이블에 따라 필터링할 수 있습니다. Cloud App Security가 클라우드 앱에 연결된 후에는 Cloud App Security 포털에서 레이블을 파일에 직접 추가하거나 분류 레이블을 거버넌스 작업으로 자동 적용하도록 파일 정책을 구성하여 Azure Information Protection 분류 레이블(보호 여부와 상관없이)을 적용하는 Azure Information Protection 통합 기능을 사용할 수 있습니다.


> [!NOTE] 
> 자동 검색에서는 다시 수정되지 않는 한 기존 파일을 검색하지 않습니다. Azure Information Protection 분류 레이블에 대한 기존 파일을 검색하려면 **콘텐츠 검사 파일 정책**이 하나 이상 있어야 합니다. 한 개도 없으면, 새 **파일 정책**을 만들고, 미리 설정된 필터를 모두 삭제한 후 **콘텐츠 검사** 옵션을 선택합니다. 그런 다음 **콘텐츠 검사** 아래의 **미리 설정된 식과 일치하는 파일 포함하기**를 클릭한 후 미리 정의된 값을 선택하고 정책을 저장합니다. 이렇게 하면 Azure Information Protection 분류 레이블을 자동으로 감지하는 콘텐츠 검사를 할 수 있습니다.

#### <a name="set-internal-and-external-tags"></a>내부 및 외부 태그 설정
기본적으로 Cloud App Security에서는 조직에 정의된 분류 레이블과 다른 조직에서 정의된 외부 레이블을 검색합니다. 


조직 외부에서 설정한 분류 레이블을 무시하려면 Cloud App Security 포털에서 **설정** 및 **Azure Information Protection** 아래로 이동합니다. **Only scan files for Azure Information Protection classification labels and content inspection warnings from this tenant**(이 테넌트의 Azure Information Protection 분류 레이블 및 콘텐츠 검사 경고에 대한 파일만 검사)를 선택합니다.
 
![레이블 무시](./media/azip-ignore.png)

### <a name="apply-labels-directly-to-files"></a>레이블을 파일에 직접 적용

1. **파일** 페이지의 **조사**에서 보호하려는 파일을 선택합니다. 파일의 행 끝에 있는 세 점을 클릭한 다음, **분류 레이블 적용**을 선택합니다.  

   ![앱 보호](./media/protect-app.png)
  
   >[!NOTE]
   > Cloud App Security는 최대 50MB인 파일에 Azure Information Protection을 적용할 수 있습니다.  

2. 파일에 적용할 조직의 분류 레이블 중 하나를 선택하라는 메시지가 표시되면 **적용**을 클릭합니다. 
   ![보호 분류 레이블](./media/protect-template.png)

3. 분류 레이블을 선택하고 적용을 클릭하면 Cloud App Security가 분류 레이블을 원본 파일에 적용합니다.

4. **분류 레이블 제거** 옵션을 선택하여 분류 레이블을 제거할 수도 있습니다. 


Cloud App Security와 Azure Information Protection이 함께 작동하는 방식에 관한 자세한 내용은 [사용자 실수로부터 데이터 보호](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake)를 참조하세요.

### <a name="automatically-label-files"></a>파일에 자동으로 레이블 지정

파일 정책을 만들고 **분류 레이블 적용**을 거버넌스 작업으로 설정하여 분류 레이블을 파일에 자동으로 적용할 수 있습니다.

다음 지침에 따라 파일 정책을 만듭니다.

1. 파일 정책을 만듭니다.
2. 검색할 파일의 형식을 포함할 정책을 설정합니다. 예를 들어 **액세스 수준**이 **내부**와 같지 않고 **소유자 OU**가 재무팀과 동일한 모든 파일을 선택합니다. 
3. 관련 앱의 거버넌스 작업에서 **분류 레이블 적용**을 클릭한 다음, 레이블 형식을 선택합니다.

   ![레이블 적용](./media/aip-gov-action.png)

> [!NOTE]
> 파일 정책을 통해 Azure Information Protection 레이블을 자동으로 적용하는 기능은 강력한 기능입니다. 고객이 많은 수의 파일에 레이블을 실수로 적용하는 것을 방지하기 위해, 안전 예방 조치로 테넌트당 앱별로 일일 **레이블 적용** 작업 100개라는 제한이 있습니다. 일일 제한에 도달하면 레이블 적용 작업이 일시 중지되고 다음날(12:00 UTC 이후) 자동으로 계속됩니다. 테넌트의 제한을 늘리려면 [Cloud App Security 지원에 문의](mailto:cascoresupport@microsoft.com)하세요.

### <a name="control-file-exposure"></a>파일 노출 제어

-  예를 들어 아래가 Azure Information Protection 분류 레이블로 레이블이 지정된 문서인 경우:

   ![샘플 Azure Information Protection 화면](./media/azip-screen.png)

- **파일** 페이지에서 Azure Information Protection 분류 레이블을 필터링하여 Cloud App Security에서 이 문서를 볼 수 있습니다.

   ![Cloud App Security 및 Azure Information Protection 비교](./media/cas-compared-azip.png)

- 파일 서랍에서 해당 파일 및 해당 파일의 분류 레이블에 대한 자세한 정보를 얻을 수 있습니다. **파일** 페이지에서 관련 파일을 클릭하여 분류 레이블이 있는지 확인합니다.

   ![파일 서랍](./media/azip-file-drawer.png)

- 그런 다음 Cloud App Security에서 파일 정책을 만들어 부적절하게 공유된 파일을 제어하고 레이블이 지정되어 최근에 수정된 파일을 찾을 수 있습니다.

- 특정 파일에 분류 레이블을 자동으로 적용하는 정책을 만들 수 있습니다.
- 또한 파일 분류에 관한 활동에 대한 경고를 트리거할 수도 있습니다.


> [!Note]
> 파일에 대해 Azure Information Protection 레이블을 사용하지 않도록 설정하면 사용하지 않도록 설정한 레이블이 Cloud App Security에서 사용 안 함으로 표시됩니다. 삭제된 레이블은 표시되지 않습니다.


**샘플 정책 - 상자에서 외부에 공유되는 기밀 데이터:**

1. 파일 정책을 만듭니다.
2. 정책의 이름, 심각도 및 범주를 설정합니다.
3. 다음 필터를 추가하여 상자에서 외부 공유된 모든 기밀 데이터 찾기:

![기밀성 정책](./media/azip-confidentiality-policy.png) 

**샘플 정책 - SharePoint의 Finance 폴더 외부에서 최근에 수정된 제한된 데이터:**

1. 파일 정책을 만듭니다.
2. 정책의 이름, 심각도 및 범주를 설정합니다.
3. 다음 필터를 추가하여 폴더 선택 옵션에서 Finance 폴더를 제외하고 최근에 수정된 모든 제한 데이터 찾기: 
 
![제한된 데이터 정책](./media/azip-restricted-data-policy.png) 

경고를 설정하거나, 사용자에게 알리거나, 이러한 정책에 즉각적인 조치를 취할 수도 있습니다.
[거버넌스 작업](governance-actions.md)에 대해 자세히 알아보세요.

[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)에 대해 자세히 알아보고 Azure Information Protection [빠른 시작 자습서](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)를 확인하세요.


 
## <a name="related-videos"></a>관련 동영상  
[Cloud App Security + Azure Information Protection 통합](https://channel9.msdn.com/Shows/Microsoft-Security/MCAS--AIP-Integrations)  

## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
