---
title: Cloud Discovery 클라우드 앱 사용의 스냅숏 보고서 만들기 | Microsoft 문서
description: 이 문서에서는 로그를 수동으로 업로드하여 Cloud Discovery 앱의 스냅숏 보고서를 만드는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 734975276a148ce541b84c4a68751b2bdb5666fb
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143652"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="create-snapshot-cloud-discovery-reports"></a>Cloud Discovery 스냅숏 보고서 만들기
자동 로그 수집기를 사용하기 전에 로그를 수동으로 업로드하여 Microsoft Cloud App Security에서 구문 분석하도록 해야 합니다.
아직 로그가 없는데 로그가 어떤 모양일지 샘플을 보고 싶다면 아래 절차에 따라 샘플로그 파일을 다운로드하여 로그가 어떤 모양일지 확인하세요.


스냅숏 보고서를 만들려면
  
1. 조직의 사용자가 인터넷에 액세스할 때 사용하는 방화벽 및 프록시에서 로그 파일을 수집합니다. 조직의 모든 사용자 활동을 나타내는 최대 트래픽 시간 동안 로그를 수집해야 합니다.  
  
2. Cloud App Security 포털에서 **검색**, **새 스냅숏 보고서 만들기**를 차례로 클릭합니다.  
  
   ![새 스냅숏 보고서 만들기](./media/create-new-snapshot-report.png)
     
3. **보고서 이름**과 **설명**을 입력합니다.
  
    ![새 스냅숏 보고서](./media/new-snapshot-report.png) 

4. 로그 파일을 업로드할 **데이터 원본**을 선택합니다.  
  
5. 로그 형식을 확인하여 다운로드할 수 있는 샘플에 따라 형식이 올바로 지정되었는지 확인합니다. **보기 및 확인**을 클릭한 다음 **샘플 로그 다운로드**를 클릭합니다. 그런 다음 로그를 제공된 샘플과 비교하여 호환되는지 확인합니다. 

   ![로그 형식 확인](./media/cloud-discovery-snapshot-verify.png)  

   > [!NOTE]
   > FTP 샘플 형식은 스냅숏 및 자동화된 업로드에서 지원되지만 syslog는 자동화된 업로드에서만 지원됩니다.<br></br>
   샘플 로그를 다운로드하면 샘플 FTP 로그가 다운로드됩니다.


6. 업로드할 **트래픽 로그를 선택**합니다. 한 번에 최대 20개 파일을 업로드할 수 있습니다. 압축된 파일도 지원됩니다.  
  
7. **만들기**를 클릭합니다.  

8. 업로드가 완료되면 로그가 성공적으로 업로드되었음을 알려주는 상태 메시지가 화면의 오른쪽 위에 나타납니다.  
  
9. 로그 파일을 업로드한 후 구문 분석하고 분석하려면 다소 시간이 걸립니다.  
   로그 파일의 처리가 완료되면 완료되었다는 메일을 받게 됩니다. 
  
10. 로그 파일의 처리 상태를 업데이트하기 위해 알림 배너가 포털 맨 위의 상태 표시줄에 나타납니다.  
    ![로그 파일 처리 메뉴 모음](./media/processing-log-file-menu-bar.png) 
   
11. 로그를 업로드하는 데 성공하고 나면 로그 파일 처리가 완료되었다는 내용의 알림이 표시됩니다. 이제 상태 표시줄의 링크를 클릭하거나 설정 코그로 이동하고 **Cloud Discovery 설정**을 선택하여 보고서를 볼 수 있습니다.   
  
     ![Discovery 설정 탭](./media/discovery-settings-tab.png)
12. 그런 다음 **스냅숏 보고서**를 선택하고 스냅숏 보고서를 선택합니다.
 
![스냅숏 보고서 관리](./media/snapshot-report-managment.png)

  
      
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
    
      
  