---
title: SIEM 통합 문제 해결 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 SIEM을 Cloud App Security에 연결할 때 발생할 수 있는 문제 목록과 각각에 대한 해결 방법을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: de64d9ca-eaed-4243-bcf7-adca5aff18c8
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 47158a4fba1027f4e1ac3bfe0a73b2b1014375e8
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568797"
---
# <a name="troubleshooting-the-siem-agent"></a>SIEM 에이전트 문제 해결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 SIEM을 Cloud App Security에 연결할 때 발생할 수 있는 문제 목록과 해결 방법을 제공합니다.

## <a name="troubleshooting"></a>문제 해결

Microsoft Cloud App Security 포털의 SIEM 에이전트 상태가 **연결 오류** 또는 **연결 끊김**이 아닌지, 에이전트 알림이 없는지를 확인합니다. 연결이 2시간을 초과하여 다운되면 상태는 **연결 오류**로 표시됩니다. 연결이 12시간을 넘게 다운되면 상태는 **연결 끊김**으로 변경됩니다.

에이전트를 실행하는 동안 cmd 프롬프트에 다음 오류 중 하나가 표시되는 경우 다음 단계를 사용하여 문제를 해결하세요.

|Error|Description|해결 방법|
|----|----|----|
|부트스트랩 중 일반 오류 발생|에이전트 부트스트랩 중 예기치 않은 오류가 발생했습니다.|지원 담당자에게 문의하세요.|
|너무 많은 중요한 오류 발생|콘솔을 연결하는 동안 너무 많은 중요한 오류가 발생했습니다. 종료합니다.|지원 담당자에게 문의하세요.|
|잘못된 토큰|제공된 토큰이 잘못되었습니다.|올바른 토큰을 복사했는지 확인합니다. 위 프로세스를 사용하여 토큰을 다시 생성할 수 있습니다.|
|잘못된 프록시 주소|제공된 프록시 주소가 잘못되었습니다.|올바른 프록시 및 포트를 입력했는지 확인합니다.|


에이전트를 만든 후에 Cloud App Security 포털에서 SIEM 에이전트 페이지를 확인합니다. 다음 **에이전트 알림** 중 하나가 표시되는 경우 다음 단계를 사용하여 문제를 해결하세요.

|Error|Description|해결 방법|
|----|----|----|
|**내부 오류**|SIEM 에이전트에 알 수 없는 오류가 발생했습니다.|지원 담당자에게 문의하세요.|
|**데이터 서버 보내기 오류**|TCP를 통해 Syslog 서버로 작업하는 경우 이 오류가 발생할 수 있습니다. SIEM 에이전트가 Syslog 서버에 연결할 수 없습니다.  이 오류가 발생할 경우 해결될 때까지 에이전트는 새 작업을 끌어오는 것을 중지합니다. 오류 표시가 중지될 때까지 수정 단계를 수행해야 합니다.|1. Syslog 서버를 올바르게 정의했는지 확인합니다. Cloud App Security UI에서 위에 설명된 대로 SIEM 에이전트를 편집합니다. 서버의 이름을 올바르게 작성하고 정확한 포트를 설정해야 합니다. </br>2. Syslog 서버에 대한 연결을 확인합니다. 방화벽이 통신을 차단하지 않는지 확인합니다.| 
|**데이터 서버 연결 오류**| TCP를 통해 Syslog 서버로 작업하는 경우 이 오류가 발생할 수 있습니다. SIEM 에이전트가 Syslog 서버에 연결할 수 없습니다.  이 오류가 발생할 경우 해결될 때까지 에이전트는 새 작업을 끌어오는 것을 중지합니다. 오류 표시가 중지될 때까지 수정 단계를 수행해야 합니다.|1. Syslog 서버를 올바르게 정의했는지 확인합니다. Cloud App Security UI에서 위에 설명된 대로 SIEM 에이전트를 편집합니다. 서버의 이름을 올바르게 작성하고 정확한 포트를 설정해야 합니다. </br>2. Syslog 서버에 대한 연결을 확인합니다. 방화벽이 통신을 차단하지 않는지 확인합니다.|
|**SIEM 에이전트 오류**|SIEM 에이전트의 연결이 X시간 이상 끊어졌습니다.|Cloud App Security 포털에서 SIEM 구성을 변경하지 않았는지 확인하세요. 그렇지 않으면 이 오류는 Cloud App Security와 SIEM을 실행 중인 컴퓨터 간의 연결 문제를 나타낼 수 있습니다.|
|**SIEM 에이전트 알림 오류**|SIEM 에이전트에서 SIEM 에이전트 알림 전달 오류가 발생했습니다.|이 오류는 SIEM 에이전트와 SIEM 서버 간 연결에 대한 오류가 수신되었음을 나타냅니다. SIEM 서버나 SIEM 에이전트를 실행 중인 컴퓨터를 차단하는 방화벽이 없는지 확인합니다. 또한 SIEM 서버의 IP 주소가 변경되지 않았는지 확인합니다.|


## <a name="next-steps"></a>다음 단계
  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
