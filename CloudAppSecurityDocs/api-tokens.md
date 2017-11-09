---
title: "Cloud App Security의 API 토큰 관리 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security용 API 토큰을 생성하는 방법을 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4f5e6b1e-6b2c-4358-98f0-945e2993d5fe
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e8e86368429fac280b5555d85a0de3ec1789effa
ms.sourcegitcommit: 2fe9475d428855a6dab6fa2edd0ccd56d66f87ec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2017
---
# <a name="api-tokens"></a>API 토큰
    
Cloud App Security API에서는 REST API 끝점을 통해 Cloud App Security에 대한 프로그래밍 방식 액세스를 제공합니다. 응용 프로그램은 API를 사용하여 Cloud App Security 데이터 및 개체에 대한 읽기 및 업데이트 작업을 수행합니다. 예를 들어 Cloud App Security API에서는 사용자 개체에 대한 다음과 같은 일반 작업을 지원합니다.

- Cloud Discovery에 대한 로그 파일 업로드
- 차단 스크립트 생성
- 활동, 경고 및 정책 보고서 나열
- 경고 해제 및 해결

API에 대한 전체 설명서를 확인하려면 Cloud App Security 포털에서 [도움말] > **API 설명서**로 이동합니다.

API에 액세스하려면 API 토큰을 만들고 소프트웨어에서 이 토큰을 사용하여 Cloud App Security API에 연결해야 합니다.

[API 토큰] 탭에서 테넌트의 모든 API 토큰을 관리할 수 있습니다. 


## <a name="generate-a-token"></a>토큰 생성

1. **설정** 메뉴에서 **보안 확장**, **API 토큰**을 차례로 선택합니다.

2. 더하기 아이콘, **새 토큰 생성**을 클릭하고, 나중에 토큰을 식별할 이름을 지정하고, **다음**을 클릭합니다.
![Cloud App Security에서 API 토큰 생성](./media/api-token-gen.png)

3. 토큰 값을 복사하고 복구를 위해 임의 위치에 저장해 둡니다. 토큰을 분실하면 토큰을 다시 생성해야 합니다. 토큰에는 토큰을 발급한 사용자의 권한이 포함됩니다. 예를 들어 보안 독자는 데이터에 대해 경고할 수 있는 토큰을 발급할 수 없습니다.

4. 활성, 비활성 또는 생성됨 상태별로 토큰을 필터링할 수 있습니다. 

  - 생성됨은 사용된 적이 없는 토큰입니다. 
  - 활성은 생성되었고 지난 7일 이내에 사용된 토큰입니다. 
  - 비활성은 사용되었지만 지난 7일 동안 활동이 없는 토큰입니다.
5. 새 토큰을 생성하고 나면 Cloud App Security 포털에 액세스하는 데 사용할 새 URL이 제공됩니다. 

 ![Cloud App Security API 토큰](./media/generate-api-token.png)

일반 포털 URL은 계속 작동하지만, 토큰과 함께 제공된 사용자 지정 URL보다 상당히 느립니다. URL을 잊은 경우 언제든지 메뉴의 **?** 아이콘으로 이동하고 **정보**를 선택하여 URL을 확인할 수 있습니다.

## <a name="api-token-management"></a>API 토큰 관리

API 토큰 페이지에는 생성된 모든 API 토큰 표가 포함됩니다.

전체 관리자는 이 테넌트에 대해 생성된 모든 토큰을 볼 수 있습니다. 기타 사용자는 직접 생성한 토큰만 볼 수 있습니다.

표에는 토큰이 생성된 시간과 마지막으로 사용된 시간에 대한 자세한 정보가 나와 있고 여기에서 토큰을 철회할 수 있습니다. 

토큰은 철회된 후 표에서 제거되고 토큰을 사용하고 있던 소프트웨어는 새 토큰이 제공될 때까지 API 호출을 실행하지 못합니다. 

> [!NOTE]
> SIEM 커넥터 및 로그 수집기에서도 API 토큰을 사용합니다. 이러한 토큰은 로그 수집기 및 SIEM 에이전트 섹션에서 관리해야 하고 이 표에는 나타나지 않습니다. 





## <a name="see-also"></a>참고 항목  
[SIEM 통합 문제 해결](troubleshooting-siem.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  

## <a name="check-out-this-video"></a>이 비디오를 확인해 보세요!
[Microsoft Cloud App Security - REST API 및 토큰](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens)  