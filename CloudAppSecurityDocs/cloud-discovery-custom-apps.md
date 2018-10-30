---
title: Cloud App Security에서 Cloud Discovery에 사용자 지정 앱 추가 | Microsoft Docs
description: 이 항목에서는 Cloud App Security에서 Cloud Discovery에 사용자 지정 앱을 추가하여 섀도 IT를 모니터링하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 98b0d841-b33d-4ae9-b48b-d9ee77785eaa
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ed32435d0add14f1db3ef8457e54a628d9b26747
ms.sourcegitcommit: 9c314d566a1dd35e32650928052b8a817dd20d9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990684"
---
*적용 대상: Microsoft Cloud App Security*

# <a name="add-custom-apps-to-cloud-discovery"></a>Cloud Discovery에 사용자 지정 앱 추가
    
Cloud Discovery는 Microsoft Cloud App Security의 클라우드 앱 카탈로그에 대한 트래픽 로그를 분석합니다. 16,000개가 넘는 클라우드 앱이 클라우드 앱 카탈로그에 위치합니다. 카탈로그에는 공개적으로 사용 가능한 클라우드 앱만 포함되어 있으며 Cloud App Security가 이러한 앱에 대한 표시 여부 및 위험 정보를 제공합니다.

클라우드 앱 카탈로그에서 제외된 클라우드 앱을 표시하기 위해 Cloud App Security를 사용하여 조직에 대해 특별히 개발되거나 할당된 사용자 지정 클라우드 앱(LOB 앱)의 사용을 검색할 수 있습니다.

새 사용자 지정 클라우드 앱을 추가하면 Cloud App Security가 업로드된 방화벽 및 프록시 트래픽 로그 메시지를 앱에 연결한 다음, 앱을 사용한 사용자 수, 앱을 사용한 고유한 원본 IP 주소 수, 앱 간에 전송된 트래픽 양과 같이 조직에서 이 앱의 사용을 Cloud Discovery 페이지에 표시합니다. 

## <a name="add-a-new-custom-cloud-app"></a>새 사용자 지정 클라우드 앱 추가

1. Cloud App Security 포털에서 **검색**, **Cloud Discovery 대시보드**를 차례로 클릭합니다. 
  
   ![Cloud Discovery 대시보드 메뉴](./media/cloud-discovery-dashboard-menu.png)

2. 오른쪽 위에 있는 3개의 점을 클릭한 다음, **새 사용자 지정 앱 추가**를 선택합니다. 

   ![사용자 지정 앱 추가 메뉴](./media/add-custom-app-menu.png)

3. 필드를 입력하여 방화벽 로그에서 검색된 후에 클라우드 앱 카탈로그 및 Cloud Discovery에 나열될 새 앱 레코드를 정의합니다.

   ![사용자 지정 앱](./media/add-custom-app.png)

4. **도메인**에서 사용자 지정 앱에 액세스할 때 사용되는 고유한 도메인을 입력합니다. 이러한 도메인은 트래픽 로그 메시지를 이 앱에 연결하는 데 사용됩니다. 사용 중인 데이터 원본에 앱 URL 정보가 포함되어 있지 않으면 **IPv4** 및 **IPv6** 주소 필드를 입력해야 합니다.
5. **호스팅 플랫폼** 및 **Azure 구독 ID**를 추가합니다. 앱의 **사업부**를 선택적으로 지정합니다. 
6. 위험 **점수**를 할당하고, **앱 메모**를 추가하여 이 레코드에 대한 변경 내용을 추적할 수 있습니다.
7. **만들기**를 클릭합니다.

앱이 만들어진 후 클라우드 앱 카탈로그에서 앱을 사용할 수 있습니다.

언제든지 행 끝에 있는 3개의 점을 클릭하여 사용자 지정 앱을 편집하거나 삭제할 수 있습니다.

>[!NOTE]
> 사용자 지정 앱의 경우 사용자가 앱을 추가한 후 **사용자 지정 앱** 태그를 사용하여 자동으로 태그가 지정됩니다. 이 앱 태그는 제거할 수 없습니다.
사용자 지정 앱을 모두 보려면 **앱 태그** 필터를 ‘사용자 지정 앱’과 동일하게 설정합니다. 
<!-- -  By default, custom apps have a risk score of 10, but you can use the **Override app score** action to change it at any time.-->

  
## <a name="next-steps"></a>다음 단계 
[사용자 활동 정책](user-activity-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  