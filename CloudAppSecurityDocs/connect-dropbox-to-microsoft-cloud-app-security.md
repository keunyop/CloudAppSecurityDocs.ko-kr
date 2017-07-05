---
title: "표시 유형 및 사용 제어를 위해 Cloud App Security에 Dropbox 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 Dropbox 앱을 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4acd93f4-b885-4e1f-a385-43b5db02a3ee
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 02cf326722410041b112caf67dc7d33cf72fe375
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2017
---
# <a name="connect-dropbox-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Dropbox 연결
이 섹션에서는 커넥터 API를 사용하여 기존 Dropbox 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
 
 
Dropbox를 사용하면 로그인하지 않고 공유 링크에서 파일에 액세스할 수 있으므로 Cloud App Security에서는 이러한 사용자를 인증되지 않은 사용자로 등록합니다. 인증되지 않은 Dropbox 사용자가 표시되면 조직에 소속되지 않은 사용자를 나타내거나 조직 내에서 로그인하지 않은 사용자로 인식될 수 있습니다.

## <a name="how-to-connect-dropbox-to-cloud-app-security"></a>Cloud App Security에 Dropbox를 연결하는 방법  
  
1.  Cloud App Security 콘솔에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
2.  **앱 커넥터** 페이지에서 더하기 단추, **Dropbox**를 차례로 클릭합니다.  
  
     ![dropbox 연결](./media/connect-dropbox.png "dropbox 연결")  
  
3.  팝업에서 관리자 계정 메일 주소를 입력합니다.  
  
4.  **링크 생성**을 클릭합니다.  
  
5.  **이 링크를 따름**을 클릭합니다.  
  
     Dropbox 로그온 페이지가 열립니다. Cloud App Security에서 팀의 Dropbox 인스턴스에 액세스할 수 있도록 자격 증명을 입력합니다.  
  
6.  Dropbox에서 팀 정보 및 활동 로그에 대한 Cloud App Security의 액세스와 팀 멤버로서의 작업 수행을 허용할지 여부를 묻는 메시지를 표시합니다. 계속하려면 **허용**을 클릭합니다.  
  
7.  Cloud App Security 콘솔로 돌아가면 Dropbox가 연결되었다는 메시지가 표시됩니다.  
  
8.  **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 성공 알림을 받은 후 **닫기**를 클릭합니다.  
  
Dropbox를 연결한 후 연결 전 60일에 대한 이벤트를 받게 됩니다.

> [!NOTE] 
> 파일 추가에 대한 모든 Dropbox 이벤트는 Cloud App Security에 연결된 다른 모든 앱에 맞게 파일 업로드로 Cloud App Security에 표시됩니다. 
 
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  