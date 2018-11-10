---
title: 표시 유형 및 사용 제어를 위해 Cloud App Security에 Salesforce 연결 | Microsoft 문서
description: 이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Salesforce를 연결하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/29/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 776d7589-acdb-4cb6-99a0-3be2f7b6aab2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1a2830cb7813eb5b86fc56751f628b6b9d5a630e
ms.sourcegitcommit: bb010d8dd0a6eff39df31e33c2cc9c37ec321b46
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50217308"
---
*적용 대상: Microsoft Cloud App Security*

# <a name="connect-salesforce-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Salesforce 연결
이 섹션에서는 앱 커넥터 API를 사용하여 기존 Salesforce 계정에 Microsoft Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-salesforce-to-cloud-app-security"></a>Cloud App Security에 Salesforce를 연결하는 방법  
  
1.  Cloud App Security에 대한 전용 서비스 관리자 계정을 사용하는 것이 좋습니다.  
  
2.  Salesforce에서 REST API가 사용하도록 설정되었는지 확인합니다.  
  
     Salesforce 계정이 REST API 지원을 포함하는  
  
     **Performance**, **Enterprise**, **Unlimited** 또는 **Developer** 버전 중 하나여야 합니다.  
  
     **Professional** 버전에는 기본적으로 REST API가 없지만 요청 시 추가할 수 있습니다.  
  
     다음과 같이 버전에서 REST API를 사용할 수 있고 사용하도록 설정되었는지 확인합니다.  
  
    -   Salesforce 계정에 로그인하고 **설정** 페이지로 이동합니다.  
  
    -   **사용자 관리**에서 **사용자 프로필** 페이지로 이동합니다.  
  
         ![salesforce 사용자 관리 프로필](./media/salesforce-manageusers-profiles.png "salesforce 사용자 관리 프로필")  
  
    -   **새로 만들기**를 클릭하여 새 프로필을 만듭니다. 
    - Cloud App Security를 배포하려고 만든 프로필을 선택하고 **편집**을 클릭합니다.  프로필은 Cloud App Security 서비스 계정에서 앱 커넥터를 설정하는 데 사용됩니다.  
  
         ![salesforce 프로필 편집](./media/salesforce-edit-profile.png "salesforce 프로필 편집")  
  
    -   다음 확인란이 사용하도록 설정되었는지 확인합니다.   
        - **API 사용**
        - **모든 데이터 보기** 
        - **Manage Salesforce CRM Content**(Salesforce CRM 콘텐츠 관리)
        - **사용자 관리**
        
        이러한 확인란이 선택되지 않은 경우 Salesforce에 연락하여 계정에 추가해야 할 수 있습니다.  
             
3.  조직에서 **Salesforce CRM 콘텐츠**가 사용으로 설정된 경우 현재 관리자 계정에서도 사용으로 설정되었는지 확인합니다.  
  
    1.  Salesforce 설정 페이지로 이동합니다.  
  
         ![salesforce 설정](./media/salesforce-setup.png "salesforce 설정")  
  
    2.  측면 메뉴에서 **사용자 관리**를 선택하고 **사용자**를 클릭합니다.  
  
         ![salesforce 메뉴 사용자](./media/salesforce-menu-users.png "salesforce 메뉴 사용자")  
  
    3.  현재 관리 사용자를 전용 Cloud App Security 사용자로 선택합니다.  
  
    4.  **Salesforce CRM 콘텐츠 사용자** 확인란이 선택되었는지 확인합니다.  
  
         선택되지 않은 경우 **편집**을 클릭한 다음, 확인란을 선택합니다.  
  
         ![salesforce crm 콘텐츠 사용자](./media/salesforce-crm-content-user.png "salesforce crm 콘텐츠 사용자")  
  
    5.  **Save**을 클릭합니다.  
  
4.  Cloud App Security 콘솔에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
5.  **앱 커넥터** 페이지에서 더하기 단추, **Salesforce**를 차례로 클릭합니다.  
  
     ![salesforce 연결](./media/connect-salesforce.png "salesforce에 연결")  
  
6.  Salesforce 설정 페이지의 API 탭에서 설치하려는 인스턴스에 따라 **이 링크를 따름**을 클릭합니다.  
  
7.  그러면 Salesforce 로그인 페이지가 열립니다. Cloud App Security에서 팀의 Salesforce 앱에 액세스할 수 있도록 자격 증명을 입력합니다.  
  
     ![salesforce 로그인](./media/salesforce-logon.png "salesforce 로그온")  
  
8.  Salesforce에서 팀 정보 및 활동 로그에 대한 Cloud App Security의 액세스와 팀 멤버로서의 작업 수행을 허용할지 여부를 묻는 메시지를 표시합니다. 계속하려면 **허용**을 클릭합니다.  
  
9. 이때 배포에 대한 성공 또는 실패 알림이 표시됩니다. 이제 Salesforce.com에서 Cloud App Security에 권한이 부여되었습니다.  
  
10. Cloud App Security 콘솔로 돌아가면 Salesforce가 연결되었다는 메시지가 표시됩니다.  
  
11. **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **완료**를 클릭합니다.  
  
  
Salesforce를 연결한 후 Salesforce EventMonitoring 라이선스에 따라 연결 순간부터의 트리거, 연결 전 60일 동안의 로그인 이벤트 및 설정 감사 내역, 30일 또는 1일 전 EventMonitoring과 같은 이벤트를 받게 됩니다. Cloud App Security API는 Salesforce에서 사용 가능한 API와 직접 통신합니다. Salesforce는 수신할 수 있는 API 호출 수를 제한하므로 Cloud App Security는 제한을 고려하고 준수합니다. Salesforce API는 사용 가능하고 남은 전체 API 호출을 비롯하여 API 카운터에 대한 필드를 사용하여 각 응답을 전송합니다. Cloud App Security는 이를 백분율로 계산하고 항상 사용 가능한 API 호출의 10%를 남깁니다. 

> [!NOTE]
> Cloud App Security 제한은 Salesforce를 통해 API 호출을 하는 다른 응용 프로그램의 호출이 아니라, Salesforce를 통한 고유한 API 호출에 대해서만 계산됩니다.
> 제한으로 인해 API 호출을 제한하면 Cloud App Security에 수집되는 데이터 속도는 느려질 수 있지만 대개 하룻밤 동안 처리됩니다.


Salesforce 이벤트는 Cloud App Security에서 다음과 같이 처리합니다. 
  
- 15분마다 로그인 이벤트
- 15분마다 감사 추적 설정
- Salesforce 로그가 UTC 시간으로 오전 12시부터 오후 11시 59분까지 24시간 동안 사용 활동을 추적합니다. Salesforce의 이벤트는 실시간으로 로그 데이터를 생성합니다. 그러나 Salesforce는 이벤트가 발생한 그다음 날 사용률이 낮은 시간에 로그 파일을 생성합니다. 따라서 로그 파일 데이터는 이벤트 발생 후 적어도 하루 동안은 사용할 수 없습니다. Salesforce 이벤트에 대한 자세한 내용은 [Using Event Monitoring(이벤트 모니터링 사용)](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/using_resources_event_log_files.htm)을 참조하세요.


## <a name="next-steps"></a>다음 단계  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  