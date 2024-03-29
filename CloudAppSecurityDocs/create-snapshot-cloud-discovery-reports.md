---
title: Cloud Discovery 클라우드 앱 사용의 스냅숏 보고서 만들기
description: 이 문서에서는 로그를 수동으로 업로드하여 Cloud Discovery 앱의 스냅숏 보고서를 만드는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 04/07/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: a06200e0256bac49f8a4a4e169898dcb3a09aa7b
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568010"
---
# <a name="create-snapshot-cloud-discovery-reports"></a>Cloud Discovery 스냅숏 보고서 만들기

*적용 대상: Microsoft Cloud App Security*

자동 로그 수집기를 사용하기 전에 로그를 수동으로 업로드하고 Microsoft Cloud App Security에서 구문 분석하도록 해야 합니다. 로그 수집기가 작동하는 방법과 예상되는 로그 형식에 대한 자세한 내용은 [Cloud Discovery에 트래픽 로그 사용](#log-format)을 참조하세요.

로그가 아직 없고 로그가 어떤 모양인지 예제를 보려면 샘플 로그 파일을 다운로드합니다. 로그의 모양을 보려면 다음 절차를 따르세요.


스냅숏 보고서를 만들려면
  
1. 조직의 사용자가 인터넷에 액세스할 때 사용하는 방화벽 및 프록시에서 로그 파일을 수집합니다. 조직의 모든 사용자 활동을 나타내는 최대 트래픽 시간 동안 로그를 수집해야 합니다.  
  
2. Cloud App Security 포털에서 **검색**을 클릭한 다음, **스냅숏 보고서 만들기**를 클릭합니다.  
  
   ![새 스냅숏 보고서 만들기](./media/create-new-snapshot-report.png)
     
3. **보고서 이름**과 **설명**을 입력합니다.
  
    ![새 스냅숏 보고서](./media/new-snapshot-report.png) 

4. 로그 파일을 업로드할 **데이터 원본**을 선택합니다.  
  
5. 로그 형식을 확인하여 다운로드할 수 있는 샘플 로그에 따라 형식이 올바로 지정되었는지 확인합니다. **보기 및 확인**을 클릭한 다음, **샘플 로그 다운로드**를 클릭합니다. 로그를 제공된 샘플과 비교하여 호환되는지 확인합니다. 

   ![로그 형식 확인](./media/cloud-discovery-snapshot-verify.png)  

   > [!NOTE]
   > FTP 샘플 형식은 스냅숏 및 자동화된 업로드에서 지원되지만 syslog는 자동화된 업로드에서만 지원됩니다.<br></br>
   샘플 로그를 다운로드하면 샘플 FTP 로그가 다운로드됩니다.


6. 업로드할 **트래픽 로그를 선택**합니다. 한 번에 최대 20개 파일을 업로드할 수 있습니다. 압축된 파일도 지원됩니다.  
  
7. **만들기**를 클릭합니다.  

8. 업로드가 완료되면 로그가 성공적으로 업로드되었음을 알려주는 상태 메시지가 화면의 오른쪽 위에 나타납니다.  
  
9. 로그 파일을 업로드한 후 구문 분석하고 분석하려면 다소 시간이 걸립니다.  
   로그 파일의 처리가 완료되면 작업이 완료되었음을 알리는 이메일을 받게 됩니다. 
  
10. **Cloud Discovery 대시보드**의 맨 위에 있는 상태 표시줄에 알림 배너가 나타납니다. 배너는 로그 파일의 처리 상태를 업데이트합니다.  
    ![로그 파일 처리 메뉴 모음](./media/processing-log-file-menu-bar.png) 
   
11. 로그를 업로드하는 데 성공하고 나면 로그 파일 처리가 완료되었다는 내용의 알림이 표시됩니다. 이제 상태 표시줄의 링크를 클릭하거나 설정 코그로 이동하여 **Cloud Discovery 설정**을 선택하여 보고서를 볼 수 있습니다.   
  
     ![Discovery 설정 탭](./media/discovery-settings-tab.png)
12. 그런 다음 **스냅숏 보고서**를 선택하고 스냅숏 보고서를 선택합니다.
 
     ![스냅숏 보고서 관리](./media/snapshot-report-managment.png)

  
## Cloud Discovery에 트래픽 로그 사용 <a name="log-format"></a>
Cloud Discovery에서는 트래픽 로그의 데이터를 사용합니다. 로그가 더 자세할수록 더 명확하게 파악할 수 있습니다. Cloud Discovery에는 다음과 같은 특성이 있는 웹 트래픽 데이터가 필요합니다.
- 트랜잭션 날짜
- 원본 IP
- 원본 사용자 - 권장
- 대상 IP 주소
- 대상 URL **권장**(URL은 IP 주소보다 클라우드 앱 검색에 더 높은 정확도를 제공함)
- 총 데이터 양(데이터 정보는 매우 중요함)
- 업로드하거나 다운로드한 데이터 양(클라우드 앱의 사용 패턴에 대한 통찰력 제공)
- 수행된 작업(허용/차단)

Cloud Discovery에서는 로그에 포함되지 않은 특성을 표시하거나 분석할 수 없습니다.
예를 들어 **Cisco ASA Firewall** 표준 로그 형식에는 **트랜잭션당 업로드된 바이트 수**, **사용자 이름** 및 **대상 URL**(대상 IP만)이 없습니다.
따라서 이러한 특성은 이러한 로그에 대한 Cloud Discovery 데이터에 표시되지 않으며 클라우드 앱에 대한 가시성이 제한됩니다. Cisco ASA Firewall의 경우 정보 수준을 6으로 설정해야 합니다. 


Cloud Discovery 보고서를 성공적으로 생성하려면 트래픽 로그가 다음 조건을 충족해야 합니다.
1. [데이터 원본이 지원 됩니다](set-up-cloud-discovery.md#supported-firewalls-and-proxies)합니다.
2. 로그 형식은 예상되는 표준 형식과 일치합니다(로그 도구로 업로드 시 확인되는 형식).
3. 이벤트가 90일보다 오래되지 않았습니다.
4. 로그 파일이 유효하며 아웃바운드 트래픽 정보를 포함합니다.


 
## <a name="next-steps"></a>다음 단계  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
    
      
  
