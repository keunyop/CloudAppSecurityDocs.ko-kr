---
title: "표시 유형 및 사용 제어를 위해 Cloud App Security에 Azure 연결 | Microsoft Docs"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Azure를 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 75b5a6fb3707872f0455da1a1856b55adb17c597
ms.sourcegitcommit: f9851779aa15b11f559e56ac818f1333f027c000
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2017
---
# <a name="connect-azure-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Azure 연결

이 섹션에서는 앱 커넥터 API를 사용하여 기존 Azure 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>Cloud App Security에 연결을 위해 Azure 설정

Cloud App Security는 Event Hubs를 통해 Azure에 연결됩니다. 이 섹션에서는 모든 활동 로그를 구독의 단일 이벤트 허브로 스트리밍하기 위한 지침을 제공합니다. 

### <a name="step-1-stream-your-azure-activity"></a>1단계: Azure 활동 스트림

1.  Azure 구독의 Azure 활동 로그를 이벤트 허브에 스트림합니다. Azure 설명서에서 공식 지침을 따릅니다. https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

 > [!NOTE]
 > Azure 구독이 여러 개 있는 경우 각 구독에 대해 이 단계를 반복하지만 구독에서 공유되는 이벤트 허브는 하나만 사용합니다.

 지침을 완료하면 새 이벤트 허브가 선택한 네임스페이스에 만들어집니다.

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>2단계: 이벤트 허브에 연결 문자열 가져오기

1.  Event Hubs 블레이드로 이동합니다.
  
   ![Event Hubs 블레이드](media/azure-event-hubs.png "Azure Event Hubs")

2.  이벤트 허브 네임스페이스를 선택합니다.
  
    ![이벤트 허브 네임스페이스](media/azure-namespace.png "Azure 네임스페이스")

3.  메뉴에서 **엔터티** 아래의 **Event Hubs**를 클릭합니다. 
  
    ![Event Hubs 엔터티](media/azure-event-hubs-entities.png "Azure Event Hubs 엔터티")

4.  Azure Monitor에서 만든 새 이벤트 허브를 선택합니다. 이름이 **insights-operational-logs**입니다.
  
    ![Insights 작업 로그](media/azure-insight-operational-logs.png "Azure Insight 작업 로그")

5. **Shared access policies**\(공유 액세스 정책\)를 클릭한 다음 **추가**를 클릭하여 이벤트 허브에서 읽을 수 있는 Cloud App Security 권한을 제공하는 새 액세스 정책을 만듭니다.
  
    ![공유 액세스 정책](media/azure-shared-access-policies.png "Azure 공유 액세스 정책")

6.  새 정책의 이름을 입력하고 **수신 클레임**을 포함되는지 확인합니다. 완료했으면 **만들기**를 클릭합니다.
  
    ![Azure 새 정책](media/azure-new-policy.png "Azure 새 정책 만들기")

7.  **설정**, **Shared access policies**\(공유 액세스 정책\)에서 방금 만든 액세스 정책을 클릭합니다.   
  
    ![Azure 정책 선택](media/azure-select-policy.png "Azure 정책 선택")

8. [정책] 창에서 **연결 문자열 - 기본 키** 또는 **연결 문자열 - 보조 키** 옆의 단추를 클릭하여 연결 문자열 하나를 복사합니다.

### <a name="step-3-add-azure-to-cloud-app-security"></a>3단계: Cloud App Security에 Azure 추가
 
1.  Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
3.  **앱 커넥터** 페이지에서 더하기 기호 단추를 클릭하고 **Microsoft Azure**를 선택합니다.  
  
     ![Cloud App Security에 Azure 연결](media/azure-connect-app.png "Azure 연결")  
  
4.  **연결 문자열** 필드에서 이전 단계에서 복사한 연결 문자열을 붙여넣습니다.  
  
5.  사용할 다른 소비자 그룹을 만든 경우가 아니라면 **소비자 그룹** 필드에 $Default를 입력합니다.
  
6.  **연결**을 클릭합니다.
8.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  





## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  