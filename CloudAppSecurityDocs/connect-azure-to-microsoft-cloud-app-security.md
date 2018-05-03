---
title: 표시 유형 및 사용 제어를 위해 Cloud App Security에 Azure 연결 | Microsoft Docs
description: 이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Azure를 연결하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 417e5eb128e5ec351369d8703a3c220117031f32
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2018
---
*적용 대상: Microsoft Cloud App Security*


# <a name="connect-azure-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Azure 연결

이 섹션에서는 앱 커넥터 API를 사용하여 기존 Azure 계정에 Microsoft Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>Cloud App Security에 연결을 위해 Azure 설정

Cloud App Security는 Event Hubs를 통해 Azure에 연결됩니다. 이 섹션에서는 모든 활동 로그를 구독의 단일 이벤트 허브로 스트리밍하기 위한 지침을 제공합니다. 

### <a name="step-1-stream-your-azure-activity-logs-to-event-hubs"></a>1단계: Azure 활동 로그를 Event Hubs에 스트림

1. Azure 구독의 Azure 활동 로그를 이벤트 허브에 스트림합니다. Azure 설명서의 공식 지침(https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs)을 따릅니다.

   > [!NOTE]
   > Azure 구독이 여러 개 있는 경우 구독에서 공유되는 하나의 이벤트 허브를 사용하여 각 구독에 대해 이 단계를 반복합니다.

   지침을 완료하면 새 이벤트 허브가 선택한 네임스페이스에 만들어집니다.
 
   > [!NOTE]
   > 활동 로그를 내보내려고 한 후 오류가 발생하면 왼쪽 메뉴에서 Azure의 **리소스 공급자**로 이동하여 ‘microsoft.insights’가 등록되었는지 확인합니다.

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>2단계: 이벤트 허브에 연결 문자열 가져오기

1. 왼쪽 메뉴의 **Event Hubs - 미리 보기**로 이동합니다.
  
   ![Event Hubs 메뉴](media/azure-event-hubs.png "Azure Event Hubs")

2. 이벤트 허브 네임스페이스를 선택합니다.
  
   ![이벤트 허브 네임스페이스](media/azure-namespace.png "Azure 네임스페이스")

3. 메뉴에서 **엔터티** 아래의 **Event Hubs**를 클릭합니다. 
  
   ![Event Hubs 엔터티](media/azure-event-hubs-entities.png "Azure Event Hubs 엔터티")

4. Azure Monitor에서 만든 새 이벤트 허브를 선택합니다. 이름이 **insights-operational-logs**입니다.
   > [!NOTE]
   > 이벤트 허브가 만들어질 때까지 몇 분 정도 걸릴 수 있습니다.

   ![Insights 작업 로그](media/azure-insight-operational-logs.png "Azure Insight 작업 로그")
  
  
5. **Shared access policies**\(공유 액세스 정책\)를 클릭한 다음 **추가**를 클릭하여 이벤트 허브에서 읽을 수 있는 Cloud App Security 권한을 제공하는 새 액세스 정책을 만듭니다.
  
    ![공유 액세스 정책](media/azure-shared-access-policies.png "Azure 공유 액세스 정책")

6. 새 정책의 이름을 입력하고 **수신 클레임**을 포함되는지 확인합니다. 완료했으면 **만들기**를 클릭합니다.
  
   ![Azure 새 정책](media/azure-new-policy.png "Azure 새 정책")

7. **설정**, **공유 액세스 정책**에서 직접 만든 액세스 정책을 클릭합니다.   
  
   ![Azure 정책](media/azure-select-policy.png "Azure 정책")

8. [정책] 창에서 **연결 문자열 - 기본 키** 또는 **연결 문자열 - 보조 키** 옆의 단추를 클릭하여 연결 문자열 하나를 복사합니다.

### <a name="step-3-add-azure-to-cloud-app-security"></a>3단계: Cloud App Security에 Azure 추가
 
1. Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
2. **앱 커넥터** 페이지에서 더하기 기호 단추를 클릭하고 **Microsoft Azure**를 선택합니다.  
  
    ![Cloud App Security에 Azure 연결](media/azure-connect-app.png "Azure 연결")  
  
3. **연결 문자열** 필드에서 이전 단계에서 복사한 연결 문자열을 붙여넣습니다.  
  
4. **소비자 그룹** 필드에 `$Default`를 입력합니다.
    
   >[!NOTE] 
   > 사용할 다른 소비자 그룹을 만든 경우 해당 **소비자 그룹** 이름을 사용합니다.
  
5. **연결**을 클릭하여 연결을 설정하고 테스트합니다. 이 작업에는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  


> [!NOTE]
> 이 기능은 비공개 미리 보기입니다.


## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  