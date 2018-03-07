---
title: "Cloud App Security에서 Cloud Discovery에 사용자 지정 앱 추가 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security에서 Cloud Discovery에 사용자 지정 앱을 추가하여 섀도 IT를 모니터링하는 방법을 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/27/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 98b0d841-b33d-4ae9-b48b-d9ee77785eaa
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d8ccd44e3c488b9adb0d4cd9df96b29b6bcc3e2d
ms.sourcegitcommit: 85d90d51e9e265d077f38b0188bcfdab2ce63ed1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="add-custom-apps-to-cloud-discovery"></a>Cloud Discovery에 사용자 지정 앱 추가
    
Cloud Discovery는 15,000개 이상의 클라우드 앱이 포함된 Microsoft Cloud App Security 클라우드 앱 카탈로그에 대한 트래픽 로그를 분석합니다. 카탈로그에는 공개적으로 사용 가능한 클라우드 앱만 포함되어 있으며 Cloud App Security가 이러한 앱에 대한 표시 여부 및 위험 정보를 제공합니다.

클라우드 앱 카탈로그에서 제외된 클라우드 앱을 표시하기 위해 Cloud App Security를 사용하여 조직용으로 특별히 개발되거나 할당된 사용자 지정 클라우드 앱(LOB 앱)의 사용을 검색할 수 있습니다.

새 사용자 지정 클라우드 앱을 추가하면 Cloud App Security가 업로드된 방화벽 및 프록시 트래픽 로그 메시지를 앱에 연결한 다음 앱을 사용한 사용자 수, 앱을 사용한 고유한 소스 IP 주소 수, 앱으로/에서 전송된 트래픽 양 같이 조직에서 이루어진 이 앱의 사용을 Cloud Discovery 페이지에 표시합니다. 

새 사용자 지정 클라우드 앱을 추가하려면:

1.  Cloud App Security 포털에서 **검색**, **Cloud Discovery 대시보드**를 차례로 클릭합니다. 
  
 ![Cloud Discovery 대시보드 메뉴](./media/cloud-discovery-dashboard-menu.png)

2.  오른쪽 위에 있는 3개의 점을 클릭한 다음 **새 사용자 지정 앱 추가**를 선택합니다. 

 ![사용자 지정 앱 추가 메뉴](./media/add-custom-app-menu.png)

3.  필드를 입력하여 방화벽 로그에서 검색된 후 클라우드 앱 카탈로그 및 Cloud Discovery에 나열될 새 앱 레코드를 정의합니다.

  ![사용자 지정 앱](./media/add-custom-app.png)

4. **도메인**에서 사용자 지정 앱에 액세스할 때 사용되는 고유한 도메인을 입력합니다. 이러한 도메인은 트래픽 로그 메시지를 이 앱에 연결하는 데 사용됩니다. 사용 중인 데이터 원본에 앱 URL 정보가 포함되어 있지 않으면 **IPv4** 및 **IPv6** 주소 필드를 입력해야 합니다.
4.  이 레코드의 변경 내용을 추적할 수 있는 메모를 추가하는 것이 좋습니다.

앱이 만들어진 후 클라우드 앱 카탈로그에서 앱을 사용할 수 있습니다.

언제든지 행 끝에 있는 3개의 점을 클릭하여 사용자 지정 앱을 편집하거나 삭제할 수 있습니다.

>[!NOTE]
> - 사용자 지정 앱의 경우 사용자가 앱을 추가한 후 **사용자 지정 앱** 태그를 사용하여 자동으로 태그가 지정됩니다. 이 앱 태그는 제거할 수 없습니다.
사용자 지정 앱을 모두 보려면 **앱 태그** 필터를 ‘사용자 지정 앱’과 동일하게 설정합니다. 
> - 기본적으로 사용자 지정 앱의 위험 점수는 10점이지만 **앱 점수 재정의** 작업을 사용하여 언제든지 변경할 수 있습니다.

  
## <a name="see-also"></a>참고 항목  
[사용자 활동 정책](user-activity-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  