---
title: WebEx Cloud App Security에 연결
description: 이 문서에서는 API 커넥터를 사용 하 여 표시 유형 및 사용 제어에 대 한 Cloud App Security에 WebEx 응용 프로그램을 연결 하는 방법에 대 한 정보를 제공 합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 3/22/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c43271fd-9a61-4727-9945-de1c6ea5422c
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 09555165697ee66a84c99d4f3a5790f22b4d17d6
ms.sourcegitcommit: fe4cd2174f6dc83811a2d484f079e8dfbac5d082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476981"
---
# <a name="connect-cisco-webex-to-microsoft-cloud-app-security"></a>Cisco WebEx Microsoft Cloud App Security에 연결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 커넥터 Api를 사용 하 여 기존 Cisco WebEx 계정에 Microsoft Cloud App Security를 연결 하기 위한 지침을 제공 합니다. 이 연결 수에 대 한 가시성 및 WebEx 사용자, 활동 및 파일에 대 한 제어를 제공합니다. 
 
## <a name="prerequisites"></a>필수 구성 요소

연결에 대 한 전용된 서비스 계정을 만들어야 하는 것이 좋습니다. 이 통해 같은이 계정에서 수행 중인으로 WebEx에서 수행 된 거 버 넌 스 작업 WebEx에 전송 된 메시지를 삭제 하도록 확인할 수 있습니다. 그렇지 않으면 WebEx에 Cloud App Security를 연결 하는 관리자의 이름을 작업을 수행 하는 사용자로 표시 됩니다.  

## <a name="how-to-connect-webex-to-cloud-app-security"></a>WebEx Cloud App Security에 연결 하는 방법  
  
1.  Cloud App Security 콘솔에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
2.  에 **앱 커넥터** 페이지에서 더하기 단추를 클릭 합니다 **Cisco WebEx**합니다.  
  
     ![연결 WebEx](./media/cisco-webex.png "WebEx 연결")  
  
3.  팝업에서이 커넥터의 인스턴스 이름을 입력 합니다.  
  
4.  클릭 **Cisco Webex 연결**합니다. WebEx에 대 한 로그인 페이지를 엽니다. Cloud App Security 팀의 WebEx 인스턴스에 액세스할 수 있도록 자격 증명을 입력 합니다.  
  
6.  WebEx는 Cloud App Security 활동 로그에서 팀 정보에 대 한 액세스를 허용 하 고 팀 멤버로 서 작업을 수행 하려는 경우 요청 합니다. 계속하려면 **허용**을 클릭합니다.  
  
7.  Cloud App Security 콘솔에서 다시 WebEx가 연결 되었다는 메시지를 받게 됩니다.  
  
8.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
WebEx를 연결한 후 연결 전 7 일 동안의 이벤트를 받을 수 있습니다. Cloud App Security는 지난 3 달 동안 이벤트를 검색 합니다. 이 늘리려면 Cisco WebEx pro 라이선스가 있어야 하며 Cloud App Security 지원 티켓을 엽니다.

 
## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
