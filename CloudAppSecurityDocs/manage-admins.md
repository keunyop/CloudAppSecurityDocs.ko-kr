---
title: "Cloud App Security 포털에 대한 관리자 액세스 관리 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security 포털에 대한 관리자 액세스를 설정하는 지침을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ce7a3bb3951e16efeaeafa3e2fc463a3ac5d9dbc
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: ko-KR
---
## <a name="managing-admin-access"></a>관리자 액세스 관리

Cloud App Security에서는 다음 관리자 역할을 지원합니다.

- 전역 관리자: 전역 관리자는 **모든 권한**을 가집니다. 모든 권한을 가진 관리자는 Cloud App Security에서 관리자를 추가하고, 정책 및 설정을 추가하고, 로그를 업로드하고, 거버넌스 작업을 수행할 모든 권한을 가집니다.
- 보안 관리자: 보안 관리자는 **모든 권한**을 가집니다. 모든 권한을 가진 관리자는 Cloud App Security에서 관리자를 추가하고, 정책 및 설정을 추가하고, 로그를 업로드하고, 거버넌스 작업을 수행할 모든 권한을 가집니다.
- 보안 독자: 보안 독자는 읽기 전용 권한을 가지며 경고를 관리할 수 있습니다. 보안 독자는 다음을 수행할 수 없습니다.
      - 정책 만들기 또는 기존 정책 편집/변경 
      - 거버넌스 작업 수행 
      - 검색 로그 업로드
      - 타사 앱 금지 및 승인
      - IP 주소 범위 설정 페이지 액세스 및 보기
      - 모든 설정 페이지 액세스 및 보기 
      - 검색 설정 액세스 및 보기 
      - 앱 커넥터 페이지 액세스 및 보기
      - 거버넌스 로그 액세스 및 보기 
      - 스냅숏 보고서 관리 페이지 액세스 및 보기 

Azure Active Directory 또는 Office 365에서 이러한 역할을 가진 관리자는 Cloud App Security에서도 같은 역할을 가집니다. 관리자 역할에 대한 자세한 내용은 [Azure Active Directory에서 관리자 역할 할당](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles)을 참조하세요.

Cloud App Security에 다른 관리자를 추가하려면:

1. 설정 코그 ![설정 아이콘](./media/settings-icon.png "설정 아이콘"), **관리자 액세스 관리**를 차례로 클릭합니다. 

2. Cloud App Security에 액세스할 수 있어야 하는 관리자를 추가합니다.
  
      
3. 그 다음에 드롭다운을 클릭하여 관리자에게 부여할 액세스 유형을 **모든 권한** 또는 **보안 독자** 중에서 설정합니다.

     >[!NOTE]
      >제한된 페이지에 액세스하거나 제한된 작업을 수행하려고 하는 모든 **보안 독자**에게는 페이지에 액세스하거나 작업을 수행할 권한이 없다는 오류가 표시됩니다.

4. **닫기**를 클릭합니다.  

   >[!NOTE]
    >초대되지 않은 모든 사용자(전역, 보안, 준수 관리자 등 적절한 역할이 있음)는 다른 사용자를 Cloud App Security에 초대할 수 있습니다.
  
 ![관리자 액세스 관리](./media/manage-admin-access.png "관리자 액세스 관리")  

**관리자 권한을 재정의하려면:**

Azure Active Directory 또는 Office 365의 관리자 권한을 재정의하려면 Cloud App Security에 사용자를 수동으로 추가하고 사용자에게 역할을 할당하면 됩니다.
예를 들어 Azure Active Directory의 보안 독자인 Stephanie에게 Cloud App Security의 모든 권한을 할당하려면 Cloud App Security에 Stephanie를 수동으로 추가하고 모든 권한을 할당하여 역할을 재정의하고 Cloud App Security에서 원하는 권한을 허용합니다. 


##  <a name="Adminsettings"></a> 관리자 설정 사용자 지정  
Cloud App Security의 관리자로 기본 설정을 지정하려면 포털 메뉴 모음에서 사용자 이름을 클릭하고 **사용자 설정**을 선택하여 다음을 설정합니다.  
  
1.  **계정 설정**을 클릭합니다. 여기서 사용자에게 표시되는 포털 언어를 사용자 지정할 수 있습니다. 기본 언어로 포털을 표시하도록 설정하거나 다른 언어를 설정할 수 있습니다.  
  
     ![사용자 지정 설정이](./media/custom-user-settings.png "사용자 지정 사용자 설정")  
  
2.  **알림**을 클릭하고 시스템에서 수신하는 메일에 대한 메일 및 텍스트 알림 기본 설정을 지정합니다.  메일을 수신하려는 경고 및 위반의 심각도를 설정할 수 있습니다. 심각도는 정책별로 설정되므로 위반이 트리거되면 여기서 지정한 설정과 위반된 정책의 심각도 설정에 따라 메일 알림을 받게 됩니다. Cloud App Security에 로그온할 때 사용한 관리자 사용자 계정과 연결된 별칭으로 메일이 전송됩니다. 경고 및 알림이 전송될 때 Cloud App Security에서 문자 메시지를 보낼 수 있도록 전화 번호를 입력하고 문자 메시지를 통해 알림을 수신하려는 심각도 수준을 설정합니다.  
  
   > [!NOTE] 
   > 문자 메시지를 통해 전송되는 최대 경고 수는 하루에 전화 번호당 10개입니다. 일 수는 UTC 표준 시간대에 따라 계산됩니다. 
  
  ![알림 설정](./media/notification-settings.png "알림 설정")  
  
3. 완료되면 **저장**을 클릭합니다.  


## <a name="region-and-language-settings"></a>국가 및 언어 설정  
  
1. 포털에 사용할 기본 **언어**를 설정합니다. 특정 관리자의 언어를 수정하려면 **사용자 설정** > **계정 설정**으로 이동합니다.  
  
   ![표준 시간대 언어](./media/timezone-language.png "표준 시간대 언어")  
  
2. **마스터 표준 시간대**를 선택합니다. Cloud App Security는 데이터를 지속적으로 분석하고 집계합니다. 기본적으로 Cloud App Security 포털의 표준 시간대는 UTC로 설정되어 있습니다. Cloud App Security에서 시스템의 인시던트 날짜를 정확하게 확인할 수 있는 마스터 표준 시간대를 설정하는 것이 중요합니다. 예를 들어 활동 차트에서는 데이터가 날짜별로 구성되고 이러한 날짜는 시스템의 표준 시간대에 의해 영향을 받으므로 기본 표준 시간대를 수정하지 않을 경우 데이터가 UTC 표준 시간대에 따라 24시간 일로 구성되어 여러 시간의 오차가 발생할 수 있습니다.  
  
     ![마스터 표준 시간대](./media/master-time-zone.png "마스터 표준 시간대")  
  
## <a name="back-up-portal-settings"></a>포털 설정 백업

포털 설정을 백업하려는 경우 언제든지 이 화면에서 백업할 수 있습니다. 포털 설정 내보내기를 클릭하여 정책 규칙, 사용자 그룹 및 IP 주소 범위를 비롯한 모든 포털 설정이 포함된 json 파일을 만듭니다.  
  
![백업 콘솔](./media/backup-console.png "백업 콘솔")  
  
##  <a name="mailsettings"></a> 환경 개인 설정  
메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "설정 아이콘")을 클릭하고 **메일 설정**을 선택하여 Cloud App Security에서 관련 위반에 대한 경고 및 알림을 최종 사용자에게 보내도록 요청하는 관리자에게 보내는 메일 알림에 대한 매개 변수를 설정합니다.  
  
![메일 설정 메뉴](./media/mail-setting-menu.png "메일 설정 메뉴")  
  
다음을 구성합니다.  
  
1.  **보낸 사람 메일 주소**: 알림을 보내는 데 사용할 메일 계정입니다.  
  
     **보낸 사람 표시 이름**: 메일 메시지의 **보낸 사람** 필드에 표시하려는 이름입니다.  
  
     **회신 메일 주소**: 메시지에 회신하는 데 사용할 메일 계정입니다.  
  
     ![메일 설정 구성](./media/mail-settings-config.png "메일 설정 구성")  
  
2.  html 파일을 사용하여 시스템에서 보내는 메일 메시지를 사용자 지정하고 디자인할 수 있습니다. 템플릿에 사용되는 html 파일에는 다음이 포함되어야 합니다.  
  
    -   모든 템플릿 CSS는 템플릿에 인라인으로 포함되어야 합니다.  
  
    -   템플릿에 편집할 수 없는 다음 세 개의 자리 표시자가 있어야 합니다.  
  
         %%logo%% - 일반 설정 페이지에서 업로드된 회사 로고의 URL  
  
         %%title%% - 정책에 의해 설정된 메일 제목의 자리 표시자  
  
         %%content%% - 정책에 의해 설정된 최종 사용자에 대해 포함할 콘텐츠의 자리 표시자  
  
     다음은 샘플 메일 템플릿입니다. 
```html
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

  
3.  Click **Upload a template...** and select the file you created.  
  
     Then, click **Send a test email** to send yourself a test email to see an example of the template you created.  
     The email will be sent to the account you used to log into the portal. In the test email you will be able to see the metadata fields, the template, the email subject, the title in the email body and the content.  
  
## Single sign-on  
Cloud App Security is coupled with Azure Active Directory for authentication, provisioning, and licensing related activities. For information on how to manage single sign-on, see [Azure Active Directory federation compatibility list: third-party identity providers that can be used to implement single sign-on](https://msdn.microsoft.com/library/azure/jj679342.aspx).  


> [!NOTE] 
> If you use ExpressRoute, Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance and security. There are no configuration steps required from the customer side.  
    For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  