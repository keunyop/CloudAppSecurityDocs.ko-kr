---
title: Cloud App Security와 Flow를 통합하여 사용자 지정 경고 자동화
description: 이 문서에서는 Cloud App Security와 Flow를 통합하여 사용자 지정 경고를 자동화하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 344f92e2-6b3b-46db-bfd0-3b1016e0bc34
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 558559463df0bcb4e008d75115501c23d27cd878
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53175773"
---
# <a name="integrate-with-flow-for-custom-alert-automation---preview"></a>사용자 지정 경고 자동화를 위해 Flow와 통합 - 미리 보기

*적용 대상: Microsoft Cloud App Security*

Cloud App Security는 [Microsoft Flow](https://docs.microsoft.com/flow/getting-started)와 통합하여 사용자 지정 경고 자동화 및 오케스트레이션 플레이북을 제공합니다. Microsoft Flow에서 사용할 수 있는 [커넥터의 에코시스템](https://docs.microsoft.com/connectors/)을 사용하여 Cloud App Security에서 경고를 생성하는 경우 플레이북 트리거를 자동화할 수 있습니다. 예를 들어, Cloud App Security에서 경고가 트리거될 때 [ServiceNow 커넥터](https://docs.microsoft.com/connectors/service-now/)를 사용하여 티켓팅 시스템에서 문제를 자동으로 만들거나 승인 이메일을 보내서 사용자 지정 거버넌스 작업을 실행합니다.  

## <a name="prerequisites"></a>필수 구성 요소 

 - 유효한 [Microsoft Flow 계획](https://flow.microsoft.com/en-us/pricing)이 있어야 합니다.

## <a name="how-it-works"></a>작동 방식

Cloud App Security가 정책을 정의하는 경우 자체적으로 사용자를 일시 중단하거나 파일을 비공개로 설정하는 등 미리 정의된 거버넌스 옵션을 제공합니다. Cloud App Security 커넥터를 사용하는 Microsoft Flow에서 플레이북을 만들어 정책에 대한 사용자 지정된 거버넌스 옵션을 사용하도록 설정하는 워크플로를 만들 수 있습니다. Flow에서 플레이북이 만들어지면 Cloud App Security에서 간단히 정책과 연계하여 Flow에 경고를 보냅니다. Microsoft Flow는 조직에 대해 사용자 지정된 워크플로를 만들기 위해 여러 커넥터 및 조건을 제공합니다. 

Flow에서 [Cloud App Security 커넥터](https://docs.microsoft.com/connectors/cloudappsecurity/#/providers/microsoft.powerapps/apis/shared_cloudappsecurity/apioperations/mcas_on_alert_generated)는 자동화된 트리거 및 작업을 지원합니다(출시 예정). Cloud App Security에서 경고를 생성하는 경우 Flow가 자동으로 트리거됩니다. 작업에는 Cloud App Security에서 경고 상태를 변경하는 작업이 포함됩니다. 

## <a name="how-to-create-playbooks-with-microsoft-flow"></a>Microsoft Flow를 사용하여 플레이북을 만드는 방법

1. Cloud App Security에서 [API 토큰을 만듭니다](api-tokens.md). 

2. [Microsoft Flow 포털](https://flow.microsoft.com)로 이동하고, [**처음부터 새 흐름 만들기**](https://docs.microsoft.com/flow/get-started-logic-flow)를 선택합니다. 

3. 검색 커넥터 및 트리거에서 **Cloud App Security**를 입력하고, **경고를 생성하는 경우**를 선택합니다.

   ![경고가 생성되는 경우의 Flow](./media/flow-when-alert.png)

4. **인증 설정** 아래에 1단계의 API 토큰을 붙여넣습니다. 

5. Cloud App Security에서 정책이 경고를 생성할 때 트리거되어야 하는 워크플로를 정의합니다. 작업 및 논리 조건을 추가하거나, 사례 조건을 전환하거나 플레이북을 반복하고 저장할 수 있습니다. 

   ![Flow 워크플로](./media/flow-workflow.png)

6. Cloud App Security 포털에서 **정책**으로 이동하고, Flow에 전달하려는 경고가 포함된 정책의 행에서 세 점을 클릭하고, **설정**을 선택합니다. 
7. **경고**에서 **Flow에 경고 보내기**를 선택하고 드롭다운 메뉴에서 플레이북의 이름을 선택합니다.  

   ![Cloud App Security 포털에서 Flow 사용](./media/flow-mcas-config.png)

8. 액세스 권한을 부여받은 Cloud App Security 플레이북을 **보안 확장 프로그램** 화면에서 볼 수 있습니다. 

  
   ![Cloud App Security에서 플레이북 보기](./media/flow-extensions.png)
 
 

## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
