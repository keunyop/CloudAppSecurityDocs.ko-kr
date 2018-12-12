---
title: Cloud App Security 정책 문제 해결 | Microsoft Docs
description: 이 문서에서는 Cloud App Security에서 정책 생성 문제를 해결하기 위한 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/9/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 31c07ffe1f19de86ce23cad099bd238d254c0bab
ms.sourcegitcommit: c497253a7ab63973bb806607e5f15dece91640be
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53123179"
---
# <a name="troubleshooting-microsoft-cloud-app-security-policies"></a>Microsoft Cloud App Security 정책 문제 해결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 Cloud App Security에서 정책 생성 문제를 해결하기 위한 프로세스를 설명합니다.

## <a name="troubleshooting"></a>문제 해결

다음 차트에는 정책에 대해 표시될 수 있는 오류에 대한 설명 및 해결 방법이 있습니다.

|Error|설명|해결 방법|
|----|----|----|
| **<*이름*> 정책이 구성 오류로 인해 자동으로 비활성화되었습니다.**|Microsoft Cloud App Security에서 이 오류가 발생할 경우 지정된 정책의 구성을 수정해야 함을 의미합니다. Microsoft Cloud App Security 정책을 만들 경우 Cloud App Security 또는 보안 및 규정 준수 센터에서 만든 다른 개체(예: IP 태그 또는 사용자 지정 중요한 형식)를 활용합니다. 정책에 사용한 IP 태그 또는 사용자 지정 중요한 형식을 삭제할 경우 정책이 자동으로 비활성화되며 이 오류가 표시됩니다. 이 메시지는 너무 복잡한 필터와 같은 좀 더 일반적인 구성 오류를 나타낼 수도 있습니다. |정책을 복원하려면 정책을 편집하고 언급된 모든 구성 오류를 해결합니다. 이 오류는 일반적으로 정책 필터에서 삭제된 개체를 제거하고 정책을 저장해야 함을 의미합니다.|

## <a name="next-steps"></a>다음 단계

[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)

