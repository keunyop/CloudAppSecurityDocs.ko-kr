---
title: Cloud App Security 관리자 격리를 사용하여 파일 보호
description: 이 자습서에서는 관리자 격리를 사용하여 데이터 위반을 제어하는 시나리오를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 1/27/2019
ms.topic: tutorial
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3fc04cfb-ad4c-4ac2-980a-ee9f4c740d88
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 71bb83bfbd40f39ebbd58dba6c630a2fee02927c
ms.sourcegitcommit: 9553aed06ebb2378d44bb5685439ae5cba605171
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65047812"
---
# <a name="tutorial-protect-files-with-admin-quarantine"></a>자습서: 관리자 격리를 사용하여 파일 보호

*적용 대상: Microsoft Cloud App Security*

[파일 정책](data-protection-policies.md)은 정보 보호 정책에 대한 위협을 찾는 데 유용한 도구입니다. 예를 들어 사용자가 클라우드에서 중요한 정보, 신용 카드 번호 및 타사 ICAP 파일을 저장한 위치를 찾는 파일 정책을 만듭니다. 

이 자습서는 Microsoft Cloud App Security를 사용하여 클라우드에 저장된 원하지 않는 파일을 검색하여 취약한 상태로 만드는 것을 돕고, **관리자 격리**를 사용하여 클라우드에서 파일을 보호하고, 문제를 해결하며, 향후 누출이 발생하지 않도록 함으로써 즉각적인 조치를 취하고 위협에 처한 파일을 추적하고 잠급니다.



> [!div class="checklist"]
> * 격리 작동 방식 이해 
> * 관리자 격리 설정


## <a name="understand-how-quarantine-works"></a>격리 작동 방식 이해 

>[!NOTE] 
> - 이것은 미리 보기 기능입니다.
> - 관리자 격리를 지원하는 앱 목록은 [거버넌스 작업](governance-actions.md) 목록을 참조하세요.
> - SharePoint 또는 OneDrive의 파일이 멜웨어로 감지되면 Cloud App Security 포털에 격리되지 않습니다. 

1. 파일이 정책과 일치하는 경우 파일에 **관리자 격리** 옵션을 사용할 수 있습니다.

2. 다음 작업 중 하나를 수행하여 파일을 격리합니다.
   - **관리자 격리** 작업을 수동으로 적용합니다.
     
     ![격리 작업](./media/quarantine-action.png)

   - 정책에서 자동화된 격리 작업으로 설정합니다. 

     ![자동 격리](./media/quarantine-automated.png)

3. **관리자 격리**가 적용되면 다음 작업이 자동으로 수행됩니다.

   1. 원본 파일이 설정한 관리자 격리 폴더로 이동합니다.
   2. 원본 파일이 삭제됩니다.
   3. 삭제 표식이 원본 파일 위치에 업로드됩니다.
      
      ![격리 삭제 표식](./media/quarantine-tombstone.png)
      
   4. 사용자는 삭제 표식 파일에만 액세스할 수 있습니다. 파일에서 IT를 제공하여 파일을 릴리스할 수 있는 상관 관계 ID 및 IT에서 제공된 사용자 지정 지침을 읽을 수 있습니다.

4. 파일이 격리되었다는 경고가 표시되면 Cloud App Security **경고** 페이지에서 파일을 조사합니다.
   
   ![격리 경고](./media/quarantine-alerts.png)
   
5. 또한 **격리됨** 탭의 **정책 보고서**에서:
   
   ![격리 보고서](./media/quarantine-report.png)
    
6. 파일이 격리된 후 다음 프로세스를 사용하여 위협 상황을 해결합니다.
    
    1. SharePoint Online의 격리된 폴더에서 파일을 검사합니다.
    2. 감사 로그를 확인하여 파일 속성을 심층 분석할 수도 있습니다.
    3. 파일이 회사 정책을 위반한 것으로 확인하면 조직의 IR(인시던트 응답) 프로세스를 실행합니다.
    4. 파일에 해가 없는 경우 격리에서 파일을 복원할 수 있습니다. 이 때 원래 파일이 해제됩니다. 즉, 원래 위치에 다시 복사되고, 삭제 표식이 삭제되고, 사용자는 파일에 액세스할 수 있습니다.
       
       ![격리 복원](./media/quarantine-restore.png)
       
7. 정책이 원활하게 실행되는지 유효성을 검사합니다. 그런 다음, 정책에서 자동 거버넌스 작업을 사용하여 미래의 누수를 방지하고 정책이 일치하는 경우 관리자 격리의 자동 적용을 방지합니다.

> [!NOTE]
> 파일을 복원할 경우:
> - 원본 공유가 복원되지 않고 기본 폴더 상속이 적용됩니다.
> - 복원된 파일에는 가장 최근 버전만 포함됩니다.
> - 격리 폴더 사이트 액세스 관리는 고객의 책임입니다.


## <a name="set-up-admin-quarantine"></a>관리자 격리 설정

1. 위반을 감지하는 파일 정책을 설정합니다. 이러한 정책 유형의 예제는 다음과 같습니다.

    - SharePoint Online에서 분류 레이블과 같은 메타데이터 전용 정책
    - 신용 카드 번호를 검색하는 정책과 같은 기본 DLP 정책 
    - Vontu를 찾는 정책과 같은 ICAP 타사 정책

2. 격리 위치 설정:
   1. Office 365 SharePoint 또는 비즈니스용 OneDrive의 경우 ![격리 설정](./media/quarantine-warning.png)을 지정할 때까지 정책의 일부로 파일을 관리자 격리에 넣을 수 없습니다.

      관리자 격리 설정을 지정하려면 설정 코그 아래에서 **설정**으로 이동합니다. 격리된 파일의 위치 및 해당 파일이 격리될 경우 사용자에게 표시되는 사용자 알림을 제공합니다. 
      ![격리 설정](./media/quarantine-settings.png)

   2. Box의 경우 격리 폴더 위치 및 사용자 메시지를 사용자 지정할 수 없습니다. 폴더 위치는 Box를 Cloud App Security에 연결한 관리자의 드라이브이며 사용자 메시지는 다음과 같습니다. 이 파일은 회사의 보안 및 규정 준수 정책을 위반할 수 있기 때문에 관리자 드라이브에 격리되었습니다. 도움이 필요하면 IT 관리자에게 문의하세요.



## <a name="next-steps"></a>다음 단계 
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
