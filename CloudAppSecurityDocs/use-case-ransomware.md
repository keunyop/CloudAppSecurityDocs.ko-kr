---
title: 위협 방지 시나리오 개요 - Cloud App Security | Microsoft Docs
description: 이 항목에서는 조직이 클라우드 환경에서 발생할 수 있는 위험 요소를 방지하기 위한 시나리오를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 12/14/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 7a06a243-9ec2-4a11-8db2-bc065cdfef64
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 0cb5f3ef6e88a35e7c8c5e262e666fb3d4107159
ms.sourcegitcommit: 8ef0438fa35916c48625ff750cb85e9628d202f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56282752"
---
# <a name="protecting-your-organization-from-ransomware"></a>랜섬웨어로부터 조직 보호

*적용 대상: Microsoft Cloud App Security*

최근 대규모의 랜섬웨어 공격에서 WannaCry가 사이버 세계를 심각하게 공격하여 150여 개 국가에 200,000대의 컴퓨터가 감염된 것으로 추정됩니다. 지난 몇 년 동안 랜섬웨어 공격이 증가하면서 2015년 매월 평균 25,000회 공격이, 2016년 56,000회 공격이 발생하여 네트워크와 클라우드가 위험에 처하지 않도록 사전에 대처하는 사이버 보안이 필수가 되고 있습니다. 이 문서에서는 Cloud App Security를 사용하여 클라우드를 모니터링하고, 위협을 검색 및 완화하고, 랜섬웨어로부터 환경을 보호하기 위한 모범 사례를 적용하는 방법을 설명합니다.

## <a name="what-is-ransomware"></a>랜섬웨어란?
랜섬웨어는 공격자가 사용자의 컴퓨터 액세스 차단하고 사용자의 파일을 암호화할 수 있는 파일을 보내는 사이버 공격입니다. 경우에 따라 파일은 랜섬(대가 지급)을 위해 보류되지만 컴퓨터, 파일 또는 중요 LOB 앱에 대한 액세스를 복원하기 위해 공격자에게 대가를 지급할 때까지 암호 해독되지 않습니다. 랜섬웨어 공격은 컴퓨터, 집, 사무실, 네트워크 또는 서버에 영향을 미칠 수 있습니다. 실제로 대규모 조직은 네트워크에 랜섬웨어를 전파하는 파일을 무심코 열 수 있는 많은 사용자로 구성되므로 조직은 랜섬웨어를 중지하고 컴퓨터나 파일에 대한 액세스를 복원하기 위해 공격자에게 대가를 지급해야 하는 훨씬 더 큰 위험에 놓여 있습니다.

>[!NOTE]
> 이 사용 사례는 Office 365, G Suite, Box 및 Dropbox에 적용됩니다.

## <a name="the-threat"></a>위협
조직의 사용자는 랜섬웨어 공격의 대상입니다. 사용자는 모르고 감염된 이메일을 열고 클라우드에 동기화된 파일을 포함하여 모든 파일을 감염시키는 랜섬웨어를 실행할 수 있습니다.

## <a name="the-solution"></a>해결 방법
의심스러운 활동이 검색될 때 업데이트하는 정책을 만들어 클라우드 환경에서 잠재적인 랜섬웨어를 검색하고 랜섬웨어 파일이 클라우드에 저장되지 않도록 방지하는 자동화된 작업을 설정합니다.

## <a name="out-of-the-box-protection"></a>기본 제공 보호

하나 이상의 클라우드 앱(Office 365, G Suite, Box 및 Dropbox)을 Cloud App Security에 [연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)합니다.

1.  기본적으로 Cloud App Security는 네트워크를 검색하여 사용자가 클라우드에서 일반적으로 수행하는 작업에 대한 패턴과 이 작업을 수행하는 시기 및 사용자가 일반적으로 수행하는 작업을 파악하는 기준을 설정합니다. 

2. Cloud App Security의 자동화된 [위협 검색 정책](anomaly-detection-policy.md)은 연결되는 시점부터 백그라운드에서 실행되기 시작합니다. 이러한 정책 중 하나는 랜섬웨어 활동을 검색하여 정교한 랜섬웨어 공격으로부터 포괄적인 보호를 보장합니다. 보안 연구 전문 지식을 통해 랜섬웨어 활동을 반영하는 동작 패턴을 식별하는 Cloud App Security는 전체적이고 강력한 보호를 보장합니다. 예를 들어 Cloud App Security에서 비율이 높은 파일 업로드 또는 파일 삭제 활동을 식별하는 경우 이는 부정적인 암호화 프로세스를 나타낼 수 있습니다. 이 데이터는 연결된 API에서 받은 로그에 수집된 후 알려진 랜섬웨어 확장과 같은 학습된 동작 패턴 및 위협 인텔리전스와 결합됩니다. 




## <a name="next-steps"></a>다음 단계 

[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
