---
title: "위협 방지 시나리오 개요 | Microsoft 문서"
description: "이 항목에서는 조직이 클라우드 환경에서 발생할 수 있는 위험 요소를 방지하기 위한 시나리오를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/30/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: fcc793f0fea71ef0666a7c99034185c5cd5fd894
ms.sourcegitcommit: 7e9ae94cb4f90fbccaa84f19bdebb4652a425e45
translationtype: HT
---
# <a name="controlling-and-protecting-your-files"></a>파일 제어 및 보호  

위험 수준이 높은 사용 및 클라우드 보안 문제를 식별하고 비정상적인 사용자 동작을 감지하고 사용 권한 클라우드 앱에서 발생할 수 있는 위험을 방지합니다. 사용자 및 관리자 활동을 파악하고 위험하다고 간주하는 특정 활동이 사용 권한 부여 환경에서 발생하는 경우 또는 의심스러운 동작에 대해 자동으로 경고하는 정책을 정의합니다. 방대한 양의 Microsoft 위협 인텔리전스 및 보안 연구 데이터를 활용합니다. 위협 검색 정책을 통해 사용 권한 앱에 필요한 보안 제어가 모두 구현되어 있는지 확인하고 지속적으로 앱을 제어할 수 있습니다.
 
## <a name="massive-quantities-of-files-are-being-downloaded-insider-data-exfiltration"></a>방대한 양의 파일이 다운로드됨(참가자 데이터 반출)

이 사용 사례는 Office 365, Google Apps, Box, Dropbox, Salesforce에 적용됩니다.

### <a name="the-threat"></a>위협
손상된 계정을 사용하는 공격자가 여러 파일을 다운로드하거나 액세스하여 Office 365 또는 다른 클라우드 앱에서 데이터를 반출할 수 있습니다.

### <a name="the-solution"></a>해결 방법
사용자가 짧은 기간 내에 엄청난 수의 파일을 다운로드하거나 액세스하는 경우를 감지합니다.

#### <a name="prerequisites"></a>필수 구성 요소

하나 이상의 클라우드 앱을 Cloud App Security에 [연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)합니다.

#### <a name="setting-up-monitoring"></a>모니터링 설정

1.    기본적으로 Cloud App Security는 네트워크를 검색하여 사용자가 클라우드에서 일반적으로 수행하는 작업에 대한 패턴과 이 작업을 수행하는 시기 및 사용자가 일반적으로 수행하는 작업을 파악하는 기준을 설정합니다. 

2. 또한 클라우드 앱에서 많은 양의 다운로드가 발생하는지 감시하고 일반적인 범위를 벗어나는 동작이 발생하는 경우 경고하는 정책을 설정하여 클라우드 앱 모니터링을 시작해야 합니다.

    1. **정책** 페이지에서 [ **활동 정책 만들기**](user-activity-policies.md)를 클릭합니다. 
    ![활동 정책 만들기](./media/create-activity-policy.png)

    2. [**정책 템플릿**](policy-template-reference.md) 필드에서 **단일 사용자의 대량 다운로드**를 선택합니다.
    
    3. 필요에 따라 반복 활동 필터를 미세 조정합니다.
    
    4. **템플릿 적용**을 클릭합니다. 
    ![활동 정책 템플릿](./media/activity-policy-template.png)
     
2. 일치 항목 조사
    
    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동해 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하고 파일 서랍을 열어 일치 항목을 조사할 수 있습니다. 서랍에서 이 활동이 일치하는 다른 정책을 확인할 수 있습니다. 
     


#### <a name="validating-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 연결된 클라우드 앱에서 여러 문서를 정책 구성에 정의된 대로 짧은 기간에 여러 번(예: 30분 이내에 10번) 다운로드합니다.
3. 정책 보고서로 이동합니다. 활동 정책 일치 항목이 곧 나타납니다. 
4. 일치 항목을 클릭하여 다운로드된 파일을 확인할 수 있습니다. 일치 항목 자체는 중요한 데이터를 보호하기 위해 마스킹됩니다. 

#### <a name="removing-the-risk"></a>위험 제거

유효성을 검사하고 정책을 세밀하게 조정한 후 정책과 일치할 수 있는 가능한 거짓 긍정을 제거하세요. 그런 후 다음을 수행합니다. 
  1. 행의 끝부분에 있는 세 개의 점을 클릭하고 **사용자 격리에 넣기**와 같은 적절한 거버넌스 작업을 선택하여 [거버넌스 작업](governance-actions.md)을 즉시 수행할 수 있습니다.

 ![자동 거버넌스 외부](./media/auto-gov-external.png)

   2. 완전하게 유효성을 검사한 후 자동 거버넌스 작업을 수행하도록 설정할 수 있습니다. 예를 들어 SharePoint 및 OneDrive에서 **외부 사용자 제거** 또는 **사용자 격리에 넣기**를 수행하고, G Suite 및 Box의 경우 **외부 사용자 제거** 및 **공용 액세스 제거**를 수행할 수 있습니다.

  ![자동 거버넌스 작업 적용](./media/apply-automatic-gov-actions.png)



## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  