---
title: "일반 설정 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security를 시작 및 실행하는 첫 번째 단계에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2d39b26629579905ea30f3f769ca2a16121d51d1
ms.openlocfilehash: b617a488dec97deb7c1e1d89cbaa62e496e18891


---

# <a name="general-setup"></a>일반 설정
다음 절차에서는 클라우드 환경에서 작동하도록 [!INCLUDE[Adallom1](./includes/adallom1_md.md)]를 설정하기 위한 지침을 제공합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
-   조직에서 제품을 사용하려면 Cloud App Security에 대한 라이선스가 있어야 합니다. 자세한 내용은 [Cloud App Security를 구입하는 방법](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx) 및 [라이선싱 리소스](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx)를 참조하세요.  
  
     테넌트 정품 인증 지원에 대한 자세한 내용은 [비즈니스용 Office 365 지원 문의 - 관리자 도움말](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)을 참조하세요.  
  
> [!NOTE] 
> Cloud App Security에는 Office 365 라이선스가 필요하지 않습니다.  
  
-   Cloud App Security 라이선스를 구입하면 정품 인증 정보와 Cloud App Security 포털에 대한 링크가 포함된 메일을 받게 됩니다.  
  
-   Cloud App Security를 설정하려면 Azure Active Directory 또는 Office 365에서 전역 관리자, 준수 관리자 또는 보안 관리자여야 합니다. Office 365 포털, Azure 클래식 포털 또는 Windows PowerShell용 Azure AD 모듈을 통해 역할을 할당하는지에 관계없이 관리자 역할이 할당된 사용자가 조직이 구독한 모든 클라우드 앱에서 동일한 권한을 가진다는 것을 이해하는 것이 중요합니다. 자세한 내용은 [Office 365에서 관리자 역할 할당](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) 및 [Azure Active Directory에서 관리자 역할 할당](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/)을 참조하세요.  
  
-   Cloud App Security 포털을 실행하려면 Internet Explorer 11, Microsoft Edge(최신 버전), Google Chrome(최신 버전), Mozilla Firefox(최신 버전) 또는 Apple Safari(최신 버전)을 사용합니다.  
  
## <a name="set-up-the-portal"></a>포털 설정  
  
1.  Cloud App Security 포털에 액세스하려면 [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)으로 이동합니다.  
  
     또는 관리 센터 아이콘 ![O365 관리 센터 아이콘](./media/o365-admin-centers-icon.png "O365 admin centers icon"), **Cloud App Security**를 차례로 클릭하여 **Office 365 관리 센터**를 통해 포털에 액세스할 수 있습니다.  
  
     ![O365에서 액세스](./media/access-from-o365.png "Access from O365")  
  
2.  Cloud App Security 포털 메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "settings icon")을 클릭하고 **일반 설정**을 선택하여 다음을 구성합니다.  
  
3.  **조직 정보**  
  
     조직에 대한 **조직 표시 이름**을 제공하는 것이 중요합니다. 이 이름은 시스템에서 전송하는 메일 및 웹 페이지에 표시됩니다.  
  
     **환경 이름**(테넌트)을 제공합니다. 이는 여러 테넌트를 관리하는 경우에 특히 중요합니다.  
  
     **관리되는 도메인** 목록을 추가합니다. 관리되는 도메인은 Cloud App Security에서 내부 사용자, 외부 사용자, 공유해야 하는 파일 및 공유하면 안 되는 파일을 확인하는 데 도움이 됩니다. 이 정보는 보고서와 경고에 사용됩니다.  
> [!NOTE] 
> 내부로 구성되지 않은 도메인의 사용자는 외부로 표시되며 활동이나 파일이 검색되지 않습니다.
   
시스템에서 전송하는 메일 알림과 웹 페이지에 표시되는 **로고**를 제공할 수도 있습니다. 로고는 최대 크기가 150 x 50 픽셀인 투명 배경의 png 파일이어야 합니다.  
  
4.  **활동 로그 메일 개인 정보 설정**  
  
     Exchange Online에서 메일 메시지가 검색된 경우 개인 정보를 유지하기 위해 표시 방법을 설정할 수 있습니다. 메일 메시지와 함께 **마스킹된 제목 줄**, **전체 제목 줄** 또는 **ID만** 표시하도록 설정할 수 있습니다.  
  
     ![일반 설정](./media/general-settings.png "general settings")  
  
5.  **국가 및 언어 설정**  
  
     포털에 사용할 기본 **언어**를 설정합니다. 특정 관리자의 언어를 수정하려면 **사용자 설정** > **계정 설정**으로 이동합니다.  
  
     ![표준 시간대 언어](./media/timezone-language.png "timezone language")  
  
     **마스터 표준 시간대**를 선택합니다. Cloud App Security는 데이터를 지속적으로 분석하고 집계합니다. 기본적으로 Cloud App Security 포털의 표준 시간대는 UTC로 설정되어 있습니다. Cloud App Security에서 시스템의 인시던트 날짜를 정확하게 확인할 수 있는 마스터 표준 시간대를 설정하는 것이 중요합니다. 예를 들어 활동 차트에서는 데이터가 날짜별로 구성되고 이러한 날짜는 시스템의 표준 시간대에 의해 영향을 받으므로 기본 표준 시간대를 수정하지 않을 경우 데이터가 UTC 표준 시간대에 따라 24시간 일로 구성되어 여러 시간의 오차가 발생할 수 있습니다.  
  
     ![마스터 표준 시간대](./media/master-time-zone.png "master time zone")  
  
6.  포털 설정을 백업하려는 경우 언제든지 이 화면에서 백업할 수 있습니다. 포털 설정 내보내기를 클릭하여 정책 규칙, 사용자 그룹 및 IP 주소 범위를 비롯한 모든 포털 설정이 포함된 json 파일을 만듭니다.  
  
     ![백업 콘솔](./media/backup-console.png "backup console")  
  
7.  Cloud App Security에 관리자를 추가하려면 설정 코그 ![설정 아이콘](./media/settings-icon.png "settings icon"), **관리자 액세스 관리**를 차례로 클릭합니다. Cloud App Security에 액세스할 수 있어야 하는 관리자를 추가하고 **닫기**를 클릭합니다.  
>[!NOTE]
>초대되지 않은 모든 사용자(전역, 보안, 준수 관리자 등 적절한 역할이 있음)는 다른 사용자를 Cloud App Security에 초대할 수 있습니다.
  
![관리자 액세스 관리](./media/manage-admin-access.png "manage admin access")  
  
##  <a name="a-nameadminsettingsa-customize-your-admin-settings"></a><a name="Adminsettings"></a> 관리자 설정 사용자 지정  
Cloud App Security의 관리자로 기본 설정을 지정하려면 포털 메뉴 모음에서 사용자 이름을 클릭하고 **사용자 설정**을 선택하여 다음을 설정합니다.  
  
1.  **계정 설정**을 클릭합니다. 여기서 사용자에게 표시되는 포털 언어를 사용자 지정할 수 있습니다. 기본 언어로 포털을 표시하도록 설정하거나 다른 언어를 설정할 수 있습니다.  
  
     ![사용자 지정 사용자 설정](./media/custom-user-settings.png "custom user settings")  
  
2.  **알림**을 클릭하고 시스템에서 수신하는 메일에 대한 메일 및 텍스트 알림 기본 설정을 지정합니다.  메일을 수신하려는 경고 및 위반의 심각도를 설정할 수 있습니다. 심각도는 정책별로 설정되므로 위반이 트리거되면 여기서 지정한 설정과 위반된 정책의 심각도 설정에 따라 메일 알림을 받게 됩니다. Cloud App Security에 로그온할 때 사용한 관리자 사용자 계정과 연결된 별칭으로 메일이 전송됩니다. 경고 및 알림이 전송될 때 Cloud App Security에서 문자 메시지를 보낼 수 있도록 전화 번호를 입력하고 문자 메시지를 통해 알림을 수신하려는 심각도 수준을 설정합니다.  
  
> [!NOTE] 
> 문자 메시지를 통해 전송되는 최대 경고 수는 하루에 전화 번호당 10개입니다. 일 수는 UTC 표준 시간대에 따라 계산됩니다. 
  
  ![알림 설정](./media/notification-settings.png "notification settings")  
  
  
3. 완료되면 **저장**을 클릭합니다.  
  
##  <a name="a-nameiptagsandrangesa-organize-the-data-according-to-your-needs"></a><a name="IPtagsandRanges"></a> 필요에 따라 데이터 구성  
실제 사무실 IP 주소 등 알려진 IP 주소를 쉽게 식별하려면 로그 및 경고를 표시 및 조사하는 방법에 태그를 지정하고 적절하게 분류 및 사용자 지정할 수 있도록 IP 주소 범위를 설정해야 합니다.   
각 IP 범위 그룹을 IP 범주의 사전 설정 목록에 따라 분류하거나 직접 만든 IP 태그를 사용하여 태그를 지정할 수 있습니다. 또한 이 설정을 통해 내부 네트워크 지식에 따라 공용 지리적 위치 정보를 재정의할 수 있습니다.  
  
IPv4 및 IPv6이 지원됩니다.  
  
메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "settings icon")을 클릭하고 **IP 주소 범위**를 선택합니다. **+IP 주소 범위 추가**를 클릭하고 다음을 설정합니다.  
  
> [!NOTE]  
>  위치 및 등록된 ISP가 기본값을 재정의합니다.   
> 그러나 IP 태그는 데이터를 재정의하지 않고 활동에 추가됩니다.  
  
1.  IP 범위에 **이름**을 지정합니다. 이 이름은 활동 로그에 표시되지 않고 IP 범위를 관리하는 데만 사용됩니다.  
  
     IP 범위를 IP 범주에 포함하려면 드롭다운 메뉴에서 범주를 선택합니다.  
  
2.  구성하려는 **IP 주소 범위**를 입력하고 "+" 단추를 클릭합니다. 네트워크 접두사 표기법(CIDR 표기법이라고도 함, 예: 192.168.1.0/32)을 사용하여 IP 주소 및 서브넷을 원하는 개수만큼 추가할 수 있습니다.  
  
3.  이러한 주소의 **위치** 또는 조직(ISP) 필드를 재정의하려면 새 값을 입력합니다. 예를 들어 공개적으로는 아일랜드에 있다고 간주되는 IP 주소가 있지만 실제로 미국에 있다는 것을 알고 있는 경우 이 설정을 재정의할 수 있습니다.  
  
4.  **등록된 ISP**를 입력합니다. 활동의 데이터가 재정의됩니다.  
  
5.  이러한 IP 주소의 작업에 **태그**를 지정하려면 태그를 입력합니다. 상자에 단어를 입력하면 태그가 생성됩니다. 이미 구성된 태그가 있으면 목록에서 선택하여 다른 IP 범위에 쉽게 추가할 수 있습니다. 각 범위에 대해 IP 태그를 원하는 개수만큼 추가할 수 있습니다. 정책을 만들 때 IP 태그를 사용할 수 있습니다.  
  
     기본 제공 Cloud App Security **IP 태그**는 위험한 주소에 대해 설정되며 지속적으로 업데이트됩니다. 이러한 태그에는 익명 프록시, 위성 공급자, TOR 출구 노드 및 Cloud App Security 프록시 네트워크가 포함됩니다. 이러한 기본 제공 태그는 표시되지 않습니다.  
  
6.  **IP 범주**는 관심 있는 IP 주소의 활동을 쉽게 인식하는 데 사용됩니다. 범주는 포털에서 사용할 수 있지만 사용자 구성에서 각 범주에 포함되는 IP 주소를 결정해야 합니다. 단, 익명 프록시와 TOR이라는 두 개의 IP 태그를 포함하는 "위험" 범주는 제외됩니다.  
  
     다음 IP 범주를 사용할 수 있습니다.  
  
    -   **관리**: 관리자의 모든 IP 주소여야 합니다.  
  
    -   **내부**: 내부 네트워크, 지점 및 Wi-Fi 로밍 주소의 모든 IP 주소여야 합니다.  
  
    -   **위험**: 위험한 것으로 간주하는 모든 IP 주소여야 합니다. 여기에는 과거에 본 적이 있는 의심스러운 IP 주소, 경쟁업체의 네트워크에 있는 IP 주소 등이 포함될 수 있습니다.  
  
    -   **VPN**: 원격 작업자에 사용하는 모든 IP 주소여야 합니다.  
  
    -   **클라우드 프록시**: 클라우드에 있는 프록시의 IP 주소여야 합니다.  
  
7.  완료되면 **만들기**를 클릭합니다.  
  
     ![newipaddress 범위](./media/newipaddress-range.png "newipaddress range")  
  
##  <a name="a-nameadallommailsettingsa-personalize-your-experience"></a><a name="Adallom_mailsettings"></a> 환경 개인 설정  
메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "settings icon")을 클릭하고 **메일 설정**을 선택하여 Cloud App Security에서 관련 위반에 대한 경고 및 알림을 최종 사용자에게 보내도록 요청하는 관리자에게 보내는 메일 알림에 대한 매개 변수를 설정합니다.  
  
![메일 설정 메뉴](./media/mail-setting-menu.png "mail setting menu")  
  
다음을 구성합니다.  
  
1.  **보낸 사람 메일 주소**: 알림을 보내는 데 사용할 메일 계정입니다.  
  
     **보낸 사람 표시 이름**: 메일 메시지의 **보낸 사람** 필드에 표시하려는 이름입니다.  
  
     **회신 메일 주소**: 메시지에 회신하는 데 사용할 메일 계정입니다.  
  
     ![메일 설정 구성](./media/mail-settings-config.png "mail settings config")  
  
2.  html 파일을 사용하여 시스템에서 보내는 메일 메시지를 사용자 지정하고 디자인할 수 있습니다. 템플릿에 사용되는 html 파일에는 다음이 포함되어야 합니다.  
  
    -   모든 템플릿 CSS는 템플릿에 인라인으로 포함되어야 합니다.  
  
    -   템플릿에 편집할 수 없는 다음 세 개의 자리 표시자가 있어야 합니다.  
  
         %%logo%% - 일반 설정 페이지에서 업로드된 회사 로고의 URL  
  
         %%title%% - 정책에 의해 설정된 메일 제목의 자리 표시자  
  
         %%content%% - 정책에 의해 설정된 최종 사용자에 대해 포함할 콘텐츠의 자리 표시자  
  
     다음은 샘플 메일 템플릿입니다.  
  
    ```  
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
    <html>  
    <head>  
      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>  
      <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
    </head>  
    <body class="end-user">  
    <table border="0" cellpadding="20%" cellspacing="0" width="100%" id="background-table">  
      <tr>  
        <td align="center">  
          <!--[if (gte mso 9)|(IE)]>  
          <table width="600" align="center" cellpadding="0" cellspacing="0" border="0">  
            <tr>  
              <td>  
          <![endif]-->  
          <table bgcolor="#ffffff" align="center" border="0" cellpadding="0" cellspacing="0" style="padding-bottom: 40px;" id="container-table">  
            <tr>  
              <td align="right" id="header-table-cell">  
                <img src="%%logo%%" alt="Microsoft Cloud App Security" id="org-logo" />  
              </td>  
            </tr>  
            <tr>  
              <td style="padding-top: 58px;" align="center" valign="top">  
                <table width="100%" cellpadding="12">  
                  <tr>  
                    <td align="center" class="round-title">  
                      %%title%%  
                    </td>  
                  </tr>  
                </table>  
              </td>  
            </tr>  
            <tr>  
              <td style="padding: 0 40px 79px 40px;" class="content-table-cell" align="left" valign="top">  
                  %%content%%  
              </td>  
            </tr>  
            <tr>  
              <td class="last-row"></td>  
            </tr>  
          </table>  
          <!--[if (gte mso 9)|(IE)]>  
          </td>  
          </tr>  
          </table>  
          <![endif]-->  
        </td>  
      </tr>  
    </table>  
    </body>  
    </html>  
  
    ```  
  
3.  **템플릿 업로드...**를 클릭하고 만든 파일을 선택합니다.  
  
     **테스트 전자 메일 보내기**를 클릭하여 자신에게 테스트 메일을 보낸 다음 직접 만든 템플릿의 예를 확인합니다.  
     포털에 로그인할 때 사용한 계정으로 메일이 전송됩니다. 테스트 메일에서 메타데이터 필드, 템플릿, 메일 제목, 메일 본문의 제목 및 콘텐츠를 볼 수 있습니다.  
  
## <a name="single-sign-on"></a>Single Sign-On  
Cloud App Security는 인증, 프로비전 및 라이선싱 관련 활동을 위해 Azure Active Directory와 결합되어 있습니다. Single Sign-On을 관리하는 방법에 대한 자세한 내용은 [Azure Active Directory 페더레이션 호환성 목록: Single Sign-On을 구현하는 데 사용할 수 있는 타사 ID 공급자](https://msdn.microsoft.com/library/azure/jj679342.aspx)를 참조하세요.  


> [!NOTE] 
> ExpressRoute를 사용할 경우, Cloud App Security는 Azure에 배포되고 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)와 완전히 통합됩니다. 검색 로그 업로드를 포함하여 Cloud App Security에 전송된 Cloud App Security 앱 및 트래픽과의 모든 상호 작용은 대기 시간, 성능 및 보안 향상을 위해 ExpressRoute **공용 피어링**을 통해 라우팅됩니다. 고객 측에서 필요한 구성 단계는 없습니다.  
    공용 피어링에 대한 자세한 내용은 [ExpressRoute 회로 및 라우팅 도메인](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/)을 참조하세요.  
    
## <a name="see-also"></a>참고 항목  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO2-->


