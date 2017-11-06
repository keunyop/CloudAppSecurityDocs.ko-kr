---
title: "연결된 앱에서 사용자 그룹 가져오기 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security로 사용자 그룹 가져오기에 대한 지침을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 87b831ef-5977-4df8-bed3-3ee54a8adbb5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9d8276ca9c73a18b4c9e0c3bc3ae0e604720984e
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2017
---
# <a name="import-user-groups"></a>사용자 그룹 가져오기

API 커넥터를 사용하여 앱을 연결할 때 Cloud App Security를 사용하면 Office 365 및 Azure Active Directory에서 사용자 그룹을 가져올 수 있습니다.
사용자 그룹에는 다음과 같은 두 종류가 있습니다. 
- 자동 그룹 </br>자동 그룹은 기본적으로 Cloud App Security에서 만듭니다. 예를 들어 조직 외부에 있고 파일에 대한 액세스 권한이 있는 모든 앱의 모든 사용자를 결합하거나 테넌트의 사용자 활동에 있는 모든 사용자를 결합하는 **External**(외부)이라고 하는 자동 사용자 그룹이 있습니다.
 다음 자동 그룹이 Cloud App Security에 있습니다.
  - 외부
  - Dropbox 관리자
  - Office 365 관리자
  - G Suite 관리자
  - Box 관리자
  - 모든 Salesforce 표준 및 사용자 지정 프로필(예: Salesforce 시스템 관리자). 전체 목록은 [여기](https://help.salesforce.com/articleView?id=standard_profiles.htm&language=en&type=0)를 확인하세요.

- 가져온 그룹</br>연결된 앱에서 그룹을 가져올 수 있습니다. 예를 들어 Office 365(Active Directory) 및 기타 연결된 앱에서 사용자 그룹을 가져올 수 있습니다. 그러면 전체 조직이나 특정 사용자를 확인하지 않고 특정 그룹을 확인하여 조직의 위협을 찾을 수 있습니다. 

가져온 사용자 그룹은 일반적으로 HR 직원이 보는 문서 조사, 임원 그룹에서 비정상적인 문제가 발생했는지 여부 확인 또는 관리자 그룹의 멤버가 미국 외부에서 활동을 수행했는지 확인 등의 시나리오에서 활용할 수 있습니다. 사용자 그룹을 가져오려면 다음과 같이 합니다.

1. 메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "설정 아이콘")을 클릭하고 **User groups**(사용자 그룹)를 선택합니다.
2. **Import user group**(사용자 그룹 가져오기)을 클릭합니다.

  ![사용자 그룹 가져오기](./media/user-groups-add.png)

3. 사용자 그룹을 가져올 앱을 선택합니다. 앱 목록은 배포한 앱 커넥터에 따라 달라집니다.
4. 가져올 그룹을 선택합니다. 사용 가능한 그룹 목록은 앱 자체의 모든 기존 사용자 그룹 목록이 됩니다. 새 그룹을 추가하려는 경우 앱 자체에서 직접 추가하고 여기에 표시되면 선택해야 합니다.
4. 그룹의 크기에 따라 가져오는 데 최대 1시간이 걸릴 수 있습니다. 가져오기 프로세스가 완료되면 메일 알림을 받는 옵션을 선택할 수 있습니다.
5. 클릭 **가져오기**합니다. 그룹을 가져온 후 Cloud App Security에서 Active Directory Connect처럼 자동으로 그룹 구성원을 동기화합니다.
7. 가져오기가 완료되면 **User groups**(사용자 그룹) 페이지에서 특정 그룹을 클릭하여 그룹의 모든 구성원 목록을 볼 수 있습니다. 또한 그룹의 구성원을 클릭하여 특정 계정 세부 정보를 드릴다운하고 사용하는 앱과 사용자 및 활동의 그래프 등 계정 요약을 볼 수 있습니다.

그룹을 가져오면 **활동 로그**에서 조사하고 정책을 만들 때 해당 그룹을 필터로 선택할 수 있습니다. 

> [!NOTE]
> 사용자 그룹을 가져온 후 수행된 활동만 사용자 그룹의 구성원이 수행한 것으로 태그가 지정됩니다.

사용자 그룹 필터 사용에 대한 자세한 내용은 [활동](activity-filters.md)을 참조하세요.


    
## <a name="see-also"></a>참고 항목  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  