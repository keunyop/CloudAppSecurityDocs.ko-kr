---
title: 지원되지 않는 로그에 대해 사용자 지정 로그 파서 사용 | Microsoft 문서
description: 이 문서에서는 사용자 지정 로그 파서를 사용하여 지원되지 않는 장치의 로그를 Cloud App Security로 업로드하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/13/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a612d87e-5471-4add-b4b1-dbbb530f2b61
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d8b15a5ce0deebb90b40d5a4bcd7c1aefd9bfc8a
ms.sourcegitcommit: 77850c6777504c2478611cb71a387e7fcc5f2551
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51596816"
---
# <a name="use-a-custom-log-parser"></a>사용자 지정 로그 파서 사용

*적용 대상: Microsoft Cloud App Security*

Cloud App Security를 사용하면 로그 형식을 일치시키고 처리하도록 사용자 지정 파서를 구성할 수 있으므로, Cloud Discovery에 사용할 수 있습니다. 일반적으로 방화벽 또는 장치가 Cloud App Security에서 명시적으로 지원되지 않은 경우 사용자 지정 파서를 사용합니다. 

사용자 지정 파서를 통해 이 프로세스에 따라 지원되지 않는 방화벽에서 생성된 로그를 사용할 수 있습니다. 


 
사용자 지정 CSV 파서를 구성하려면:
1. Cloud App Security 포털에서 **검색**, **새 스냅숏 보고서 만들기**를 차례로 클릭합니다.  
  
   ![새 스냅숏 보고서 만들기](./media/create-new-snapshot-report.png)
     
2. **보고서 이름**과 **설명**을 입력합니다.
  
3. **데이터 원본**에서 **Custom log format...**(사용자 지정 로그 형식...)을 선택합니다.  

    ![새 스냅숏 보고서](./media/custom-log-upload.png)   

4. 조직의 사용자가 인터넷에 액세스할 때 사용하는 방화벽 및 프록시에서 로그를 수집합니다. 조직의 모든 사용자 활동을 나타내는 최대 트래픽 시간 동안 로그를 수집해야 합니다. 

5. 텍스트 편집기에서 처리할 로그를 엽니다. 형식을 검토하여 로그의 열 이름이 **사용자 지정 로그 형식** 화면의 필드와 일치하는지 확인합니다.

   ![사용자 지정 로그 파서](./media/log-data.png) 

6. 그 다음에 데이터를 기반으로 필드를 입력하여 데이터의 어떤 열이 Cloud App Security의 특정 필드에 상호 연결되는지 설명합니다. 제대로 상호 연결되도록 로그 파일의 열 이름을 수정해야 할 수 있습니다.
  
   > [!NOTE]
    > 필드는 대/소문자를 구분합니다. Cloud App Security 및 로그 파일에서 열 이름을 똑같이 입력해야 합니다. 또한 똑같은 날짜 형식을 선택해야 합니다.

   ![사용자 지정 로그 파서](./media/custom-log-parser.png) 


7. **Save**을 클릭합니다. 구성한 사용자 지정 로그 형식은 기본 사용자 지정 파서로 저장됩니다. 언제든지 [편집]을 클릭하여 편집할 수 있습니다.

8. **트래픽 로그 선택**에서 수정한 로그 파일을 선택하고 업로드합니다. 한 번에 최대 20개 파일을 업로드할 수 있습니다. 압축된 파일도 지원됩니다.  
  

9. **만들기**를 클릭합니다.  

10. 업로드가 완료되면 로그가 성공적으로 업로드되었음을 알려주는 상태 메시지가 화면의 오른쪽 위에 나타납니다.  
  
11. 로그 파일을 업로드한 후 구문 분석하고 분석하려면 다소 시간이 걸립니다.  
    로그 파일의 처리가 완료되면 작업이 완료되었음을 알리는 이메일을 받게 됩니다. 
  
12. **Cloud Discovery 대시보드**의 맨 위에 있는 상태 표시줄에 알림 배너가 나타납니다. 배너는 로그 파일의 처리 상태를 업데이트합니다.  
    ![로그 파일 처리 메뉴 모음](./media/processing-log-file-menu-bar.png) 
   
13. 로그를 업로드하는 데 성공하고 나면 로그 파일 처리가 완료되었다는 내용의 알림이 표시됩니다. 이제 상태 표시줄의 링크를 클릭하거나 설정 코그로 이동하여 **Cloud Discovery 설정**을 선택하여 보고서를 볼 수 있습니다.   
  
     ![Discovery 설정 탭](./media/discovery-settings-tab.png)
14. 그런 다음 **스냅숏 보고서 관리**를 선택하고 스냅숏 보고서를 선택합니다.
 
    ![스냅숏 보고서 관리](./media/snapshot-report-managment.png)

  
      




## <a name="next-steps"></a>다음 단계
 
[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[연속 보고서에 대한 자동 로그 업로드 구성](configure-automatic-log-upload-for-continuous-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)

