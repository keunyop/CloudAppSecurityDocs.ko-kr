---
title: "Google Apps 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Google apps를 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/23/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6beb9041b338406fb5b16f4bd045dbdc4592c6d9
ms.openlocfilehash: b28eaa521980cb7ec8eee94f0168ca07286533e7


---

# <a name="connect-google-apps-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Google Apps 연결
이 섹션에서는 커넥터 API를 사용하여 기존 Google Apps 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.

  
  
## <a name="configure-google-apps"></a>Google Apps 구성  
  
1.  Google Apps 슈퍼 관리자로 [https://cloud.google.com/console/project](https://cloud.google.com/console/project)에 로그인합니다.  
  
2.  **빈 프로젝트 만들기**를 클릭하여 새 프로젝트를 시작합니다.  
  
     ![google1](./media/google1.png "google1")  
  
3.  **새 프로젝트** 화면에서 다음을 수행합니다.  
  
    1.  프로젝트 이름을 **Cloud App Security for Google**로 지정합니다.  
  
    2.  업데이트를 구독할지 여부를 선택합니다.  
  
    3.  서비스 약관을 검토하고 승인합니다.  
  
    4.  **만들기**를 클릭합니다.  
  
         ![google2](./media/google2.png "google2")  
  
4.  프로젝트를 만든 후 **API 사용 및 관리**를 클릭합니다.  
  
     ![google3](./media/google3.png "google3")  
  
5.  **사용 API** 탭을 클릭하고 나열된 모든 API를 사용하지 않도록 설정합니다.  
  
     ![google5](./media/google5.png "google5")  
  
6.  **Google API** 탭을 클릭하고 다음 API를 사용하도록 설정합니다(API가 **Popular APIs(인기 API)** 목록에 표시되지 않는 경우 검색 줄 사용).  
  
     ![google8](./media/google8.png "google8")  
  
    > [!NOTE]  
    >  지금은 **자격 증명** 경고를 무시합니다.  
  
    -   관리자 SDK  
  
    -   감사 API  
  
    -   드라이브 API  
  
    -   Google Apps Marketplace SDK  
  
    -   Gmail API  
  
         ![google11 경고](./media/google11-warning.png "google11 warning")  
  
7.  **사용 API**가 5개 있어야 합니다.  
  
     ![google15](./media/google15.png "google15")  
  
8.  **자격 증명**, **OAuth 승인**을 차례로 클릭합니다.  
  
    -   **사용자에게 표시되는 제품 이름**에 **Cloud App Security for Google**을 입력합니다.  
  
    -   다른 모든 필드는 선택 사항입니다.  
  
    -   **Save**을 클릭합니다.  
  
     ![google16](./media/google16.png "google16")  
  
9. **자격 증명** 탭에서 **자격 증명 만들기** 옆에 있는 화살표를 클릭하고 **서비스 계정 키**를 선택합니다.  
  
     ![google17](./media/google17.png "google17")  
  
10. **서비스 계정**에서 **새 서비스 계정**을 선택하고 임의 이름(예: **서비스 계정 1**)을 입력합니다.  
  
     ![google19](./media/google19.png "google19")  
  
     **키 유형**에서 **P12**를 선택하고 **만들기**를 클릭합니다.  
  
     P12 인증서 파일이 다운로드됩니다. 나중에 사용하기 위해 인증서를 저장합니다.  
  
     ![google20](./media/google20.png "google20")  
  
11. **자격 증명** 탭에서 맨 오른쪽에 있는 **서비스 계정 관리**를 클릭합니다.  
  
     ![google 앱 자격 증명 서비스 계정](./media/google-apps-credentials-service-account.png "google apps credentials service account")  
  
12. 만든 서비스 계정의 오른쪽에 있는 3개의 점을 클릭하고 **편집**을 선택합니다.  
  
     ![google22](./media/google22.png "google22")  
  
13. **Enable Google Apps Domain-wide Delegation**(Google Apps 도메인 수준 위임 사용) 확인란을 선택하고 **저장**을 클릭합니다.  
  
     ![google24](./media/google24.png "google24")  
  
14. 나중에 필요하므로 서비스에 할당된 **메일 주소**를 복사합니다.  
  
     ![google25](./media/google25.png "google25")  
  
15. Google Cloud Platform 옆에 있는 세 개의 가로선을 클릭하여 Google 메뉴를 열고 **API 관리자**를 선택합니다.  
  
     ![google 메뉴](./media/google-menu.png "google menu")  
  
     **사용 API**를 선택합니다.  
  
     ![google27](./media/google27.png "google27")  
  
16. **드라이브 API** 옆에 있는 설정 코그를 클릭하고 **드라이브 UI 통합**에서 다음을 입력합니다.  
  
    -   **응용 프로그램 이름**: Cloud App Security for Google  
  
    -   **짧은 설명 및 자세한 설명**: Microsoft Cloud App Security를 통해 클라우드 응용 프로그램을 파악할 수 있으며 클라우드 응용 프로그램 사용을 제어, 조사 및 규제하고, 회사 데이터를 보호하고, 임의 클라우드 응용 프로그램에 대한 의심스러운 활동을 검색하는 데 도움이 됩니다.  
  
    -   **응용 프로그램 아이콘**에서 128x128 및 32x32 이미지를 업로드합니다.  
  
         이미지는 다음 위치에서 확인할 수 있습니다. [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
    -   **URL 열기:** 아래에 다음을 입력합니다.  
  
         https://portal.cloudappsecurity.com/#/services/11770?tab=files  
  
    -   **변경 내용 저장**을 클릭합니다.  
  
         ![google29](./media/google29.png "google29")  
  
17. **사용 API** 목록에서 **Google Apps Marketplace SDK** 옆에 있는 설정 코그 설정을 클릭하고 **구성** 탭을 선택합니다.  
  
    -   나중에 사용하기 위해 맨 위에 표시되는 **프로젝트 번호(앱 ID)**를 복사합니다.  
  
    -   **응용 프로그램 이름**: Cloud App Security for Google  
  
         **응용 프로그램 설명** 필드에 "Microsoft Cloud App Security를 통해 클라우드 앱을 파악할 수 있으며 클라우드 앱 사용을 제어, 조사 및 규제하고, 회사 데이터를 보호하고, 임의 클라우드 앱에 대한 의심스러운 활동을 검색하는 데 도움이 됩니다."라고 입력합니다.  
  
    -   **개별 설치 사용** 확인란을 선택 취소합니다.  
  
    -   **응용 프로그램 아이콘**에서 필수 이미지 4개를 구성합니다.  
  
         이미지는 다음 위치에서 확인할 수 있습니다. [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
         ![google31](./media/google31.png "google31")  
  
    -   다음 **지원 URL**을 입력합니다.  
  
        -   **서비스 약관 URL**: http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **개인 정보 취급 방침 URL**: http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   **OAuth 2.0 scopes**(OAuth 2.0 범위)에서 줄당 하나씩 다음을 입력합니다. Enter 키를 눌러 확인합니다.  
  
        -   https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
        -   https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
        -   https://www.googleapis.com/auth/drive  
  
        -   https://www.googleapis.com/auth/drive.appdata  
  
        -   https://www.googleapis.com/auth/drive.apps.readonly  
  
        -   https://www.googleapis.com/auth/drive.file  
  
        -   https://www.googleapis.com/auth/drive.metadata.readonly  
  
        -   https://www.googleapis.com/auth/drive.readonly  
  
        -   https://www.googleapis.com/auth/drive.scripts  
  
        -   https://www.googleapis.com/auth/admin.directory.user.readonly  
  
        -   https://www.googleapis.com/auth/admin.directory.user.security  
  
        -   https://www.googleapis.com/auth/admin.directory.user.alias  
  
        -   https://www.googleapis.com/auth/admin.directory.orgunit  
  
        -   https://www.googleapis.com/auth/admin.directory.notifications  
  
        -   https://www.googleapis.com/auth/admin.directory.group.member  
  
        -   https://www.googleapis.com/auth/admin.directory.group  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile  
  
        -   https://www.googleapis.com/auth/admin.directory.user  
  
    -   **변경 내용 저장**을 클릭합니다.  
  
18. 컨트롤 목록에서 **보안**을 선택합니다. 이 옵션이 표시되지 않는 경우 페이지 맨 아래에 있는 회색 막대에서 기타 컨트롤을 선택한 다음 **보안**을 선택합니다.  
  
     ![google apps 보안](./media/google-apps-security.png "google apps security")  
  
19. **API 참조**를 선택합니다.  
  
     ![google api 참조](./media/google-api-ref.png "google api ref")  
  
20. **API 액세스 사용**을 선택하고 **변경 내용 저장**을 클릭합니다.  
  
     ![google api 액세스](./media/google-api-access.png "google api access")  
  
## <a name="configure-cloud-app-security"></a>Cloud App Security 구성  
  
1.  Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
2.  **연결된 앱** 페이지 더하기 기호를 클릭하고 **Google Apps**를 선택합니다.  
  
     ![google apps 연결](./media/connect-google-apps.png "connect google apps")  
  
3.  팝업에서 다음을 입력합니다.  
  
     ![Cloud App Security의 Google Apps 구성](./media/google-apps-configuration-in-cloud-app-security.png "Google Apps Configuration in Cloud App Security")  
  
    1.  14단계에서 복사한 **Google 서비스 계정 메일 주소**  
  
    2.  17단계에서 복사한 **Google 프로젝트 번호(앱 ID)**  
  
    3.  10단계에서 저장한 **Google 인증서** P12를 업로드합니다.  
  
    4.  Google Apps 관리자의 **관리자 메일** 하나를 입력합니다.  
  
    5.  Google Apps unlimited 계정이 있는 경우 이 확인란을 선택합니다. Cloud App Security for Google Apps unlimited에서 사용할 수 있는 기능에 대한 자세한 내용은 [앱에 대해 인스턴트 표시 유형, 보호 및 거버넌스 작업 사용](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)을 참조하세요.  
  
    6.  **설정 저장**을 클릭합니다.  
  
    7.  **링크를 따라** Google Apps에 연결합니다. Google Apps가 열리고 Cloud App Security에 대한 액세스 권한을 부여하라는 메시지가 표시됩니다.  
  
         ![Google Apps 권한 부여 요청](./media/google-apps-authorization-request.png "Google Apps authorization request")  
  
    8.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
         테스트는 몇 분 정도 걸릴 수 있습니다.  
  
         성공 알림을 받은 후 **완료**를 클릭하고 Google Apps 페이지를 닫습니다.  
  
  
Google Apps를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.
  
Google Apps를 연결한 후 Cloud App Security에서 전체 검색을 수행합니다. 파일 및 사용자 수에 따라 전체 검색을 완료하려면 시간이 오래 걸릴 수 있습니다. 근 실시간 검색을 사용하려면 작업이 감지되는 파일을 검색 큐의 시작 부분으로 이동합니다. 예를 들어 편집, 업데이트 또는 공유되는 파일은 바로 검색하며 일반 검색 프로세스에 연결될 때까지 대기하지 않습니다. 단, 보거나, 미리 보거나, 인쇄하거나, 내보내는 파일과 같이 기본적으로 수정되지 않는 파일에는 적용되지 않습니다.
  
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


