---
title: "Cloud App Security 및 Azure Information Protection으로 데이터 보호 | Microsoft Docs"
description: "이 항목에서는 조직의 중요한 데이터에 대한 데이터 보호를 거의 실시간으로 설정하는 프로세스를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/22/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3d01d43-0018-40e5-b7c7-8384d37bad52
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 59d8bb7e1d06cf0d5158f75e86f6bb9eff14c7de
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2017
---
# <a name="protecting-your-organizations-data"></a>조직의 데이터 보호

정보 보호에 관해 모든 직원을 제대로 교육하려면 비용이 많이 들고 때로는 불가능할 수 있습니다. SharePoint 사이트 및 Dropbox 위치에 액세스하는 공급업체와 파트너가 많은 회사의 경우 데이터가 언제나 안전하다고 보장하기 힘듭니다. 그런 경우에 Cloud App Security와 Azure Information Protection을 함께 제공합니다. 이 통합된 클라우드 앱 슈퍼 팀을 사용하면 데이터를 거의 실시간으로 보호할 수 있습니다. 고객에게 위험할 수 있을 뿐만 아니라 여러 국가에서 PII 규정을 위반하여 조직에 잠재적인 법적 문제를 일으킬 수 있습니다.

## <a name="the-threat"></a>위협
조직의 사용자가 Box에 기밀 고객 정보 파일을 저장합니다. 사용자는 직속 팀 뿐만 아니라 공급업체, 파트너 및 회사에 가끔 들르는 방문자를 비롯하여 전체 지원 직원이 해당 Box 계정에 액세스할 수 있음을 인식하지 못합니다. 조직의 Box 계정에 대한 액세스 권한이 있는 사람은 이제 해당 정보에 액세스할 수 있습니다.

## <a name="the-solution"></a>해결 방법
중요한 파일에 Azure Information Protection 암호화를 자동으로 적용하는 정책을 설정하여 데이터를 거의 실시간으로 보호합니다.
## <a name="prerequisites"></a>필수 구성 요소

Cloud App Security에 [Box를 연결](connect-box-to-microsoft-cloud-app-security.md)합니다.

## <a name="setting-up-data-protection"></a>데이터 보호 설정

1. Box에 저장된 중요한 데이터를 암호화하는 정책을 설정하여 Box에 저장하는 데이터 보호를 시작합니다.

    1. **컨트롤** 탭에서 [**Policies**](control-cloud-apps-with-policies.md)(정책)를 클릭합니다. 
   
    2. **정책 만들기**를 클릭하고 **파일 정책**을 선택합니다.
    3. Box 데이터 보호 정책을 호출하고 **이 정책이 적용될 파일에 대한 필터 만들기** 아래에 비공개 및 중요한 데이터를 대상으로 지정합니다.<br></br>
    예를 들어 **Parent folder**(부모 폴더)와 **Customer data**(고객 데이터)가 [같음]을 선택하고 **소유자** [같음]을 선택하고 재무 팀을 선택합니다.
    4. **거버넌스**에서 **Box** 섹션을 열고 **Protect**(보호)를 선택합니다.
    5. [Cloud App Security가 Azure Information Protection과 통합되었기](azip-integration.md) 때문에 데이터를 보호하기 위해 사용할 분류 레이블을 기존 분류 레이블 목록에서 선택할 수 있습니다.
    4. **만들기**를 클릭합니다. 
   
     
2. 일치 항목 조사
    
    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동해 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하여 파일 서랍을 열어서 일치를 조사할 수 있습니다. 서랍에서 이 파일이 일치하는 다른 정책을 확인할 수 있습니다. 
     
## <a name="validating-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 Box 계정으로 이동하고 **Customer data**(고객 데이터) 폴더의 파일에 액세스를 시도합니다.
3. 정책 보고서로 이동합니다. 파일 정책 일치 항목이 곧 표시됩니다. 
4. 일치 항목을 클릭하여 보호된 파일을 확인할 수 있습니다. 일치 항목 자체는 중요한 데이터를 보호하기 위해 마스킹됩니다. 



 ## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  