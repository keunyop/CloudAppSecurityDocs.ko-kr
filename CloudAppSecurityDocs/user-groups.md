---
title: Cloud App Security의 연결된 앱에서 사용자 그룹 가져오기
description: 이 문서에서는 Cloud App Security로 연결된 앱의 사용자 그룹 가져오기에 대한 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/14/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 87b831ef-5977-4df8-bed3-3ee54a8adbb5
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 7b5ec7e2ce37442b81838f7577cf4e11b260b09d
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568758"
---
# <a name="importing-user-groups-from-connected-apps"></a>연결된 앱에서 사용자 그룹 가져오기

*적용 대상: Microsoft Cloud App Security*

API 커넥터를 사용하여 앱을 연결할 때 Microsoft Cloud App Security를 사용하면 Office 365 및 Azure Active Directory에서 사용자 그룹을 가져올 수 있습니다.
사용자 그룹에는 다음과 같은 두 종류가 있습니다. 
- 자동 그룹 </br>자동 그룹은 기본적으로 Microsoft Cloud App Security에서 만듭니다. 예를 들어 조직 외부에 있고 파일에 대한 액세스 권한이 있는 모든 앱의 모든 사용자를 결합하거나 테넌트의 사용자 활동에 있는 모든 사용자를 결합하는 **External**(외부)이라고 하는 자동 사용자 그룹이 있습니다.
 다음 자동 그룹이 Cloud App Security에 있습니다.
  - 외부
  - Dropbox 관리자
  - Office 365 관리자
  - G Suite 관리자
  - Box 관리자
  - 모든 Salesforce 표준 및 사용자 지정 프로필(예: Salesforce 시스템 관리자). 전체 목록은 [여기](https://help.salesforce.com/articleView?id=standard_profiles.htm&language=en&type=0)를 확인하세요.

- 가져온 그룹</br>연결된 앱에서 그룹을 가져올 수 있습니다. 예를 들어 Office 365(Active Directory) 및 기타 연결된 앱에서 사용자 그룹을 가져올 수 있습니다. 이러한 그룹을 통해 전체 조직이나 특정 사용자를 확인하지 않고 특정 그룹을 확인하여 조직의 위협을 찾을 수 있습니다. 

가져온 사용자 그룹을 사용하는 일반적인 시나리오에는 다음이 포함됩니다.
   - HR 직원이 보는 문서 조사
   - 경영진 그룹에서 비정상적인 일이 발생하는지 확인
   - 관리자 그룹의 사용자가 미국 외부에서 작업을 수행했는지 찾기 

## <a name="how-to-import-user-groups"></a>사용자 그룹을 가져오는 방법

1. 메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "설정 아이콘")을 클릭하고 **User groups**(사용자 그룹)를 선택합니다.
2. **Import user group**(사용자 그룹 가져오기)을 클릭합니다.

   ![사용자 그룹 가져오기](./media/user-groups-add.png)

3. 사용자 그룹을 가져올 앱을 선택합니다. 앱 목록은 배포한 앱 커넥터에 따라 달라집니다.
4. 가져올 그룹을 선택합니다. 사용 가능한 그룹 목록은 앱 자체의 모든 기존 사용자 그룹 목록이 됩니다. 새 그룹을 추가하려는 경우 앱 자체에서 직접 추가해야 합니다. 그런 다음, 그룹이 여기의 목록에 표시되면 선택합니다.
5. 그룹의 크기에 따라 가져오는 데 최대 1시간이 걸릴 수 있습니다. 가져오기 프로세스가 완료되면 메일 알림을 받는 옵션을 선택할 수 있습니다.
6. **가져오기**를 클릭합니다. 그룹을 가져온 후 Cloud App Security에서 Active Directory Connect처럼 자동으로 그룹 구성원을 동기화합니다.
7. 가져오기가 완료되면 **User groups**(사용자 그룹) 페이지에서 특정 그룹을 클릭하여 그룹의 모든 구성원 목록을 볼 수 있습니다. 그룹의 멤버를 클릭하여 특정 계정의 세부 정보를 드릴다운합니다. 사용하는 앱 및 사용자 및 해당 작업의 그래프 등 계정의 요약을 볼 수 있습니다.

그룹을 가져오면 **활동 로그**에서 조사하고 정책을 만들 때 해당 그룹을 필터로 선택할 수 있습니다. 

> [!NOTE]
> - 사용자 그룹을 가져온 후 수행된 활동만 사용자 그룹의 구성원이 수행한 것으로 태그가 지정됩니다.
> - 초기 동기화 후에 그룹은 1시간마다 업데이트됩니다.

사용자 그룹 필터 사용에 대한 자세한 내용은 [활동](activity-filters.md)을 참조하세요.


## <a name="next-steps"></a>다음 단계
 
[Cloud Discovery 설정](set-up-cloud-discovery.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
