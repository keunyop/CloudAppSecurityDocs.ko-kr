---
title: "위협 방지 시나리오 개요 | Microsoft 문서"
description: "이 항목에서는 조직이 클라우드 환경에서 발생할 수 있는 위험 요소를 방지하기 위한 시나리오를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/21/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7a06a243-9ec2-4a11-8db2-bc065cdfef64
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9359935410495345820bb509984d8533cb6fa070
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2017
---
# <a name="protecting-your-organization-from-ransomware"></a>랜섬웨어로부터 조직 보호

최근 대규모의 랜섬웨어 공격에서 WannaCry가 사이버 세계를 심각하게 공격하여 150여 개 국가에 200,000대의 컴퓨터가 감염된 것으로 추정됩니다. 지난 몇 년 동안 랜섬웨어 공격이 증가하면서 2015년 매월 평균 25,000회 공격이, 2016년 56,000회 공격이 발생하여 네트워크와 클라우드가 위험에 처하지 않도록 사전에 대처하는 사이버 보안이 필수가 되고 있습니다. 이 문서에서는 Cloud App Security를 사용하여 클라우드를 모니터링하고, 위협을 검색 및 완화하고, 랜섬웨어로부터 환경을 보호하기 위한 모범 사례를 적용하는 방법을 설명합니다.

## <a name="what-is-ransomware"></a>랜섬웨어란?
랜섬웨어는 공격자가 사용자의 컴퓨터 액세스 차단하고 사용자의 파일을 암호화할 수 있는 파일을 보내는 사이버 공격입니다. 경우에 따라 파일은 랜섬(대가 지급)을 위해 보류되지만 컴퓨터, 파일 또는 중요 LOB 앱에 대한 액세스를 복원하기 위해 공격자에게 대가를 지급할 때까지 암호 해독되지 않습니다. 랜섬웨어 공격은 컴퓨터, 집, 사무실, 네트워크 또는 서버에 영향을 미칠 수 있습니다. 실제로 대규모 조직은 네트워크에 랜섬웨어를 전파하는 파일을 무심코 열 수 있는 많은 사용자로 구성되므로 조직은 랜섬웨어를 중지하고 컴퓨터나 파일에 대한 액세스를 복원하기 위해 공격자에게 대가를 지급해야 하는 훨씬 더 큰 위험에 놓여 있습니다.

>[!NOTE]
> 이 사용 사례는 Office 365, G Suite, Box 및 Dropbox에 적용됩니다.

## <a name="the-threat"></a>위협
조직의 사용자는 랜섬웨어 공격의 대상입니다. 사용자는 모르고 감염된 메일 열고 클라우드에 동기화된 파일을 포함하여 모든 파일을 감염시키는 랜섬웨어를 실행할 수 있습니다.

## <a name="the-solution"></a>해결 방법
의심스러운 활동이 검색될 때 업데이트하는 정책을 만들어 클라우드 환경에서 잠재적인 랜섬웨어를 검색하고 랜섬웨어 파일이 클라우드에 저장되지 않도록 방지하는 자동화된 작업을 설정합니다.

## <a name="prerequisites"></a>필수 구성 요소

하나 이상의 클라우드 앱(Office 365, G Suite, Box 및 Dropbox)을 Cloud App Security에 [연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)합니다.

## <a name="setting-up-monitoring"></a>모니터링 설정

1.  기본적으로 Cloud App Security는 네트워크를 검색하여 사용자가 클라우드에서 일반적으로 수행하는 작업에 대한 패턴과 이 작업을 수행하는 시기 및 사용자가 일반적으로 수행하는 작업을 파악하는 기준을 설정합니다. 

2. 또한 클라우드 앱에서 많은 양의 다운로드가 발생하는지 감시하고 일반적인 범위를 벗어나는 동작이 발생하는 경우 경고하는 정책을 설정하여 클라우드 앱 모니터링을 시작해야 합니다.

    1. **컨트롤** 탭에서 [**템플릿**](policy-template-reference.md)을 클릭합니다. 
   
    2. [**정책 템플릿**](policy-template-reference.md) 목록에서 **잠재적인 랜섬웨어 활동**을 선택합니다. 
       ![템플릿 랜섬웨어](./media/ransomware-template.png)
    3. 이 템플릿은 랜섬웨어 공격에 일반적인 활동과 알려진 랜섬웨어와 관련된 파일 및 폴더를 기본적으로 검색하도록 디자인되어 있습니다. 필요한 경우 정책과 일치할 경우 받을 경고 유형(메일 및 텍스트 메시지)을 설정할 수 있습니다.
        ![템플릿 랜섬웨어](./media/ransomware-template-fields.png)
    4. **만들기**를 클릭합니다. 
   
     
2. 일치 항목 조사
    
    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동해 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하고 파일 서랍을 열어 일치 항목을 조사할 수 있습니다. 서랍에서 이 활동이 일치하는 다른 정책을 확인할 수 있습니다. 
     
## <a name="validating-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 30개 파일의 확장명을 .wncry로 변경하고 파일을 SharePoint 사이트에 업로드합니다.
3. 정책 보고서로 이동합니다. 활동 정책 일치 항목이 곧 나타납니다. 
4. 일치 항목을 클릭하여 다운로드된 파일을 확인할 수 있습니다. 일치 항목 자체는 중요한 데이터를 보호하기 위해 마스킹됩니다. 

## <a name="remediating-attacks-and-preventing-risk"></a>공격 해결 및 위험 방지

유효성을 검사하고 정책을 세밀하게 조정한 후 정책과 일치할 수 있는 가능한 거짓 긍정을 제거하세요. 그런 후 다음을 수행합니다. 
1. 랜섬웨어 정책과 일치하는 경우 자동화된 [거버넌스 작업](governance-actions.md)을 설정하여 문제를 해결할 수 있습니다.

2. 미래의 공격을 방지하려면 자동 거버넌스 작업을 수행하도록 정책을 설정합니다. 예를 들어 SharePoint 및 OneDrive에서 자동으로 **사용자를 일시 중단**하는 정책을 설정할 수 있습니다.

 ## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  