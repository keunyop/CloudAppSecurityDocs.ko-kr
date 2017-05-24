---
title: "메일 알림 기본 설정 | Microsoft 문서"
description: "이 문서에서는 Cloud App Security에서 보낸 메일 알림을 개인 설정하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8402cdc9-4969-4150-b567-ccc9d75e5370
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 49c2c444b0ae378584f3ddbccccf7c8b34bb50d3
ms.sourcegitcommit: 26ae7b0e1ee0ec3b2c7464a6424d4ebd1cd436ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2017
---
##  <a name="mailsettings"></a> 메일 알림 기본 설정 설정  
메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "설정 아이콘")을 클릭하고 **메일 설정**을 선택하여 Cloud App Security에서 관련 위반에 대한 경고 및 알림을 최종 사용자에게 보내도록 요청하는 관리자에게 보내는 메일 알림에 대한 매개 변수를 설정합니다.  
  
![메일 설정 메뉴](./media/mail-setting-menu.png "메일 설정 메뉴")  
  
다음을 구성합니다.  
  
1.  **보낸 사람 메일 주소**: 알림을 보내는 데 사용할 메일 계정입니다.  
  
     **보낸 사람 표시 이름**: 메일 메시지의 **보낸 사람** 필드에 표시하려는 이름입니다.  
  
     **회신 메일 주소**: 메시지에 회신하는 데 사용할 메일 계정입니다.  
  
     ![메일 설정 구성](./media/mail-settings-config.png "메일 설정 구성")  
  
2.  **메일 디자인**의 경우, html 파일을 사용하여 시스템에서 보내는 메일 메시지를 사용자 지정하고 디자인할 수 있습니다. 템플릿에 사용되는 html 파일에는 다음이 포함되어야 합니다.  
  
    -   모든 템플릿 CSS는 템플릿에 인라인으로 포함되어야 합니다.  
  
    -   템플릿에 편집할 수 없는 다음 세 개의 자리 표시자가 있어야 합니다.  
  
         %%logo%% - 일반 설정 페이지에서 업로드된 회사 로고의 URL  
  
         %%title%% - 정책에 의해 설정된 메일 제목의 자리 표시자  

         %%content%% - 정책에 의해 설정된 최종 사용자에 대해 포함할 콘텐츠의 자리 표시자  
     
3.  **템플릿 업로드...**를 클릭하고 만든 파일을 선택합니다. 

4. **테스트 전자 메일 보내기**를 클릭하여 자신에게 테스트 메일을 보낸 다음 직접 만든 템플릿의 예를 확인합니다. 포털에 로그인할 때 사용한 계정으로 메일이 전송됩니다. 테스트 메일에서 메타데이터 필드, 템플릿, 메일 제목, 메일 본문의 제목 및 콘텐츠를 볼 수 있습니다.  다음은 샘플 메일 템플릿입니다. 



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
  

  
  

  
    
## <a name="see-also"></a>참고 항목  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  