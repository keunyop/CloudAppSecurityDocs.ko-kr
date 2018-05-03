---
title: Cloud App Security 정책 문제 해결 | Microsoft Docs
description: 이 항목에서는 Cloud App Security의 정책 생성 문제 해결을 위한 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9bfc880cdaa0bf87abfd2b3b34cdf647a4aa1aaf
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2018
---
*적용 대상: Microsoft Cloud App Security*


# <a name="troubleshooting-microsoft-cloud-app-security-policies"></a>Microsoft Cloud App Security 정책 문제 해결

|Error|설명|해결 방법|
|----|----|----|
| **<policy name> 정책이 구성 오류로 인해 자동으로 비활성화되었습니다.**|Microsoft Cloud App Security에서 이 오류가 발생할 경우 명명된 정책의 구성을 수정해야 함을 의미합니다. Microsoft Cloud App Security 정책을 만들 때는 Cloud App Security 내에서 생성한 다른 개체(예: IP 태그 또는 IP 범위 필터)를 자주 사용합니다. 정책에 사용한 IP 태그 또는 범위를 나중에 삭제할 경우 정책이 자동으로 비활성화되며 이 오류가 표시됩니다. |정책을 복원하려면 정책을 편집하고 해당 필터에서 삭제된 개체를 제거하고 정책을 저장합니다.|



## <a name="see-also"></a>참고 항목
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)

