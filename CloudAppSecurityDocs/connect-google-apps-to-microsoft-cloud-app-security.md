---
title: Cloud App Security에 G Suite 연결
description: 이 문서에서는 사용에 대한 표시 유형 및 제어를 위해 API 커넥터를 사용하여 Cloud App Security에 G Suite를 연결하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: fe5156475c8f014c045b34986369e8f25f1fdd4d
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65567676"
---
# <a name="connect-g-suite-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 G Suite 연결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 커넥터 API를 사용하여 기존 G Suite 계정에 Microsoft Cloud App Security를 연결하기 위한 지침을 제공합니다. 이 연결은 G Suite 사용에 대한 표시 유형과 제어를 제공합니다. 
    
## <a name="configure-g-suite"></a>G Suite 구성  
  
1. G Suite 슈퍼 관리자로 <a href="https://cloud.google.com/console/project" target="_blank">https://cloud.google.com/console/project</a>에 로그인합니다.  
  
2. **Create project**(프로젝트 만들기)를 클릭하여 새 프로젝트를 시작합니다.  
  
    ![google1](./media/google1.png "google1")  
  
3. **새 프로젝트** 화면에서:</br>
   프로젝트 이름을 **Microsoft Cloud App Security**로 지정하고 **만들기**를 클릭합니다.  
          ![google2](./media/google2.png "google2")  
  
4. 프로젝트를 만든 후에 도구 모음에서 **Google Cloud Platform**을 클릭합니다. 맨 위의 드롭다운에서 올바른 프로젝트가 선택되었는지 확인합니다.
       
      ![google 프로젝트](./media/googleverify-project.png "googleverify 프로젝트")  

5. **API** 아래에서 **API 개요로 이동**을 클릭합니다.  
  
     ![google3](./media/google3.png "google3")  
   
7. **라이브러리**를 클릭하고 다음 API를 사용하도록 설정합니다(API가 **Popular API**(인기 API) 목록에 표시되지 않는 경우 검색 줄 사용).  
     
   -   관리자 SDK  
  
   -   감사 API  
  
   -   Google 드라이브 API  
  
   -   G Suite Marketplace SDK  
  
   -   Gmail API  
            
   ![google api](./media/google4.png "google4")  
  
   > [!NOTE]  
   >  지금은 **자격 증명** 경고를 무시합니다.  

8. 각 API에 대해 [사용]을 클릭합니다.
     ![Google APPI 사용](./media/google-api.png "google-api")  
9. 다음 API가 사용하도록 설정되어 있는지 확인합니다.
  
     ![google 사용 API](./media/google5.png "google5")  
  
10. **자격 증명**을 클릭한 후 **OAuth 동의 화면** 탭을 선택합니다.
  
    - **사용자에게 표시되는 제품 이름**에서 **Microsoft Cloud App Security**를 입력합니다.  
  
    - 다른 모든 필드는 선택 사항입니다.  
  
    - **Save**을 클릭합니다.  
  
      ![Google oauth 동의](./media/google-oauth-consent.png "google oauth 동의")  
  
11. **자격 증명** 탭에서 **자격 증명 만들기** 옆의 화살표를 클릭합니다.  
  
     ![Google 자격 증명](./media/google7.png "google7")  

12. **Service account key**(서비스 계정 키)를 선택합니다.

     ![Google 서비스 계정 키](./media/google8.png "google8")  
  
13. **Create service account key**(서비스 계정 키 만들기)에서 **New service account**(새 서비스 계정)를 선택하고 이름을 입력합니다(예: **Service account 1**). **Role**(역할)에서 **Project**(프로젝트), **Editor**(편집기)를 차례로 선택합니다. **Key type**(키 유형)에서 **P12**를 선택하고 **Create**(만들기)를 클릭합니다. P12 인증서 파일이 컴퓨터에 저장됩니다.
 
     ![Google에서 서비스 계정 키 만들기](./media/google9.png "google9")  
  
14. 나중에 필요하므로 서비스에 할당된 **Service account ID**(서비스 계정 ID)를 복사합니다.    
        
15. **자격 증명** 화면에서 맨 오른쪽에 있는 **서비스 계정 관리**를 클릭합니다.  
     
    ![G Suite 자격 증명 서비스 계정](./media/google10.png "G Suite 자격 증명 서비스 계정")  
  
16. 만든 서비스 계정의 오른쪽에 있는 3개의 점을 클릭하고 **Edit**(편집)을 선택합니다.  
  
     ![google 편집](./media/google11.png "google 편집")  
  
17. **Enable G Suite Domain-wide Delegation**(G Suite 도메인 수준 위임 사용) 확인란을 선택하고 **저장**을 클릭합니다.  
  
     ![google 서비스 계정 ID](./media/google12.png "google12")  
  
18. 제목 표시줄에서 Google Cloud Platform 옆에 있는 세 개의 가로선을 클릭하여 Google 메뉴를 엽니다. **Google Cloud Platform**을 클릭하고 왼쪽 메뉴의 **API 및 서비스** 탭을 클릭합니다.  
    
19. 열린 대시보드에서 사용 가능한 API 목록까지 아래로 스크롤하고 **Google 드라이브 API**를 클릭합니다.   
       ![Google 드라이브 선택](./media/google14.png "google14")  

20. **드라이브 UI 통합** 탭을 클릭하고 다음 정보를 입력합니다.

    - **애플리케이션 이름**: Microsoft Cloud App Security  
  
    - **간단한 설명 및 자세한 설명**(선택 사항): Microsoft Cloud App Security를 통해 클라우드 애플리케이션을 파악할 수 있으며 클라우드 애플리케이션 사용을 제어, 조사 및 규제하고, 회사 데이터를 보호하고, 임의 클라우드 애플리케이션에 대한 의심스러운 활동을 검색하는 데 도움이 됩니다.  
  
    - Google을 사용하려면 하나 이상의 애플리케이션 아이콘을 업로드해야 합니다. [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826)로 이동하여 Cloud App Security 아이콘을 포함하는 zip 파일을 다운로드합니다. 그런 다음 **애플리케이션 아이콘**에서 128x128 이미지 옆에 있는 **선택**을 클릭하고 팝업 화면으로 끌어 놓습니다. 32x32 이미지 옆에 있는 **선택**을 클릭하고 팝업 화면으로 끌어 놓습니다.  
  
    - 아래로 스크롤하고 **드라이브 통합** 섹션에서 **URL 열기:** 아래에 다음 URL을 입력합니다.  
  
       https://portal.cloudappsecurity.com/#/services/11770?tab=files  
    
      ![Google 드라이브 편집](./media/google15.png "google15")  

21. **변경 내용 저장**을 클릭합니다.

22. **사용 가능한 API** 목록으로 돌아갑니다. **G Suite Marketplace SDK**를 클릭합니다. 
      
23. **구성** 탭을 선택합니다. 
  
    -   나중에 사용하기 위해 맨 위에 표시되는 **프로젝트 번호(앱 ID)** 를 복사합니다.  
  
    -   **애플리케이션 이름** 아래에서 **Microsoft Cloud App Security**를 입력합니다.
  
         **애플리케이션 설명** 형식에서 "Microsoft Cloud App Security를 통해 클라우드 앱을 파악할 수 있으며 클라우드 앱 사용을 제어, 조사 및 규제하고, 회사 데이터를 보호하고, 임의 클라우드 앱에 대한 의심스러운 활동을 감지하는 데 도움이 됩니다."라고 입력합니다. 
    - **새 항목** 창에서 **완료**를 클릭합니다.      
     
       ![Google 새 항목](./media/google-new-item.png "Google 새 항목")  

    -   **개별 설치 사용** 확인란을 선택 취소합니다.  
  
    -   **애플리케이션 아이콘**에서 필수 이미지 4개를 구성합니다.  
  
         [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826)에서 이미지를 찾을 수 있습니다.  
  
    -   다음 **지원 URL**을 입력합니다.  
  
        -   **서비스 약관 URL**: https://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **개인정보처리방침 URL**: https://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   **OAuth 2.0 scopes**(OAuth 2.0 범위)에서 다음 URL을 복사한 후 붙여넣습니다(한 번에 하나씩 복사한 후 <Enter> 키 누르기).  
  
           https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
           https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
           https://www.googleapis.com/auth/drive  
  
           https://www.googleapis.com/auth/drive.appdata  
  
           https://www.googleapis.com/auth/drive.apps.readonly  
  
           https://www.googleapis.com/auth/drive.file  
  
           https://www.googleapis.com/auth/drive.metadata.readonly  
  
           https://www.googleapis.com/auth/drive.readonly  
  
           https://www.googleapis.com/auth/drive.scripts  
  
           https://www.googleapis.com/auth/admin.directory.user.readonly  
  
           https://www.googleapis.com/auth/admin.directory.user.security  
  
           https://www.googleapis.com/auth/admin.directory.user.alias  
  
           https://www.googleapis.com/auth/admin.directory.orgunit  
  
           https://www.googleapis.com/auth/admin.directory.notifications  
  
           https://www.googleapis.com/auth/admin.directory.group.member  
  
           https://www.googleapis.com/auth/admin.directory.group  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile  
  
           https://www.googleapis.com/auth/admin.directory.user  

    -   **Visibility**(가시성)에서 **My domain**(not public)(내 도메인(공용 아님))을 선택합니다. 
    -   **변경 내용 저장**을 클릭합니다.  
        ![google 표시 여부](./media/google-visibility.png "google 표시 여부")  
24. [admin.google.com](https://admin.google.com/)으로 이동하고 **Security**(보안)를 선택합니다. 
   
      ![google 보안](./media/googlesec.png "google 보안")  
 
25. **API 참조**를 선택합니다.  
       ![google api 사용](./media/googleapi.png "google api")  
      
26. **API 액세스 사용**을 선택하고 **변경 내용 저장**을 클릭합니다.  
  
    ![google api 참조](./media/googleapiref.png "google8")  

  
## <a name="configure-cloud-app-security"></a>Cloud App Security 구성  
  
1.  Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
2.  **연결된 앱** 페이지에서 더하기 기호를 클릭하고 **G Suite**를 선택합니다.  
       
  
3.  팝업에서 다음 정보를 입력합니다.  
  
     ![Cloud App Security의 G Suite 구성](./media/gsuite-config-cas.png "Cloud App Security의 G Suite 구성")  
  
    1.  13단계에서 복사한 **서비스 계정 ID**  
  
    2.  21단계에서 복사한 **프로젝트 번호(앱 ID)**  
  
    3.  12단계에서 저장한 **인증서** P12를 업로드합니다. 이렇게 하려면 저장한 암호가 필요합니다.  
  
    4.  G Suite 관리자의 **관리자 계정 메일** 하나를 입력합니다.  
  
    5.  G Suite Business 또는 Enterprise 계정이 있는 경우 이 확인란을 선택합니다. Cloud App Security for G Suite Business 또는 Enterprise에서 사용할 수 있는 기능에 대한 자세한 내용은 [앱에 대해 인스턴트 표시 유형, 보호 및 거버넌스 작업 사용](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)을 참조하세요.  
  
    6.  **설정 저장**을 클릭합니다.  
  
    7.  **링크를 따라** G Suite에 연결합니다. G Suite가 열리고 Cloud App Security에 대한 액세스 권한을 부여하라는 메시지가 표시됩니다.  
         
    8.  **Test now**(지금 테스트)를 클릭하여 연결에 성공했는지 확인합니다.  
  
         테스트는 몇 분 정도 걸릴 수 있습니다.  
  
         성공 알림을 받은 후 **완료**를 클릭하고 G Suite 페이지를 닫습니다.  
  
  
G Suite를 연결한 후 연결 전 60일 동안 이벤트를 받게 됩니다.
  
G Suite를 연결한 후 Cloud App Security에서 전체 검색을 수행합니다. 파일 및 사용자 수에 따라 전체 검색을 완료하려면 시간이 오래 걸릴 수 있습니다. 거의 실시간 검색을 사용하려면 작업이 감지되는 파일을 검색 큐의 시작 부분으로 이동합니다. 예를 들어 편집, 업데이트 또는 공유되는 파일은 바로 검색합니다. 이는 본질적으로 수정되지 않는 파일에는 적용되지 않습니다. 예를 들어 보거나, 미리 보거나, 인쇄하거나, 내보내는 파일은 정기적인 검색 중에 검색됩니다.
  
  
## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
