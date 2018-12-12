---
title: 관리자 격리를 사용하여 파일 위반을 조사 및 해결하는 방법에 대한 사용 사례 | Microsoft Docs
description: 이 항목에서는 관리자 격리를 사용하여 데이터 위반을 제어하는 시나리오를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/9/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3fc04cfb-ad4c-4ac2-980a-ee9f4c740d88
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 70af82b34e34ffc9c557245da7f33f4e621ca15b
ms.sourcegitcommit: c497253a7ab63973bb806607e5f15dece91640be
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53124199"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="protecting-your-files-with-admin-quarantine"></a>관리자 격리를 사용하여 파일 보호

> [!NOTE]
> 이것은 미리 보기 기능입니다.

[파일 정책](data-protection-policies.md)은 사용자가 중요한 정보, 신용 카드 번호, 타사 ICAP 파일을 클라우드에 저장한 장소를 찾는 것과 같이 정보 보호 정책에 대한 위협을 찾을 수 있는 유용한 도구입니다. Microsoft Cloud App Security를 사용하여 취약한 상태를 지속시키는 클라우드에 저장된 이러한 원하지 않는 파일을 검색할 수 있고 즉각적인 작업을 수행하여 파일을 즉시 중지하고 위협이 되는 파일을 잠글 수도 있습니다. **관리자 격리**를 사용하여 클라우드에서 파일을 보호하고 문제를 해결할 뿐 아니라 미래의 누수 발생을 방지할 수 있습니다. 

>[!NOTE] 
> 관리자 격리를 지원하는 앱 목록은 [거버넌스 작업](governance-actions.md) 목록을 참조하세요.
 
## <a name="how-quarantine-works"></a>작업을 격리하는 방법 

1. 파일이 정책과 일치하는 경우 파일에 **관리자 격리** 옵션을 사용할 수 있습니다.

2. 다음 중 하나를 수행하여 파일을 격리합니다.
   - **관리자 격리** 작업을 수동으로 적용합니다.
     
     ![격리 작업](./media/quarantine-action.png)

   - 정책에서 자동화된 격리 작업으로 설정합니다. 

     ![자동 격리](./media/quarantine-automated.png)

3. **관리자 격리**가 적용되면 다음 작업이 자동으로 수행됩니다.

   1. 원본 파일이 설정한 관리자 격리 폴더로 이동합니다.
   2. 원본 파일이 삭제됩니다.
   3. 삭제 표식이 원본 파일 위치에 업로드됩니다.
      
      ![격리 삭제 표식](./media/quarantine-tombstone.png)
      
   4. 사용자는 IT에 연락하여 파일을 릴리스할 수 있는 상관 관계 ID 및 IT에서 제공된 사용자 지정 지침을 읽을 수 있는 삭제 표식에만 액세스할 수 있습니다.

4. 파일이 격리되었다는 경고가 표시되면 Cloud App Security **경고** 페이지에서 파일을 조사합니다.
   
   ![격리 경고](./media/quarantine-alerts.png)
   
5. 또한 **격리됨** 탭의 **정책 보고서**에서:
   
   ![격리 보고서](./media/quarantine-report.png)
    
6. 파일이 격리된 후 다음 프로세스를 사용하여 위협 상황을 해결합니다.
    
    1. SharePoint Online의 격리된 폴더에서 파일을 검사합니다.
    2. 감사 로그를 확인하여 파일 속성을 심층 분석할 수도 있습니다.
    3. 파일이 회사 정책을 위반한 것으로 확인되면 조직의 IR(인시던트 응답) 프로세스를 실행합니다.
    4. 무해한 파일로 확인이 되면 격리에서 파일을 복원할 수 있고, 이때 원본 파일이 릴리스됩니다. 즉, 파일이 다시 원래 위치로 복사되고, 삭제 표식이 삭제되고, 사용자가 파일에 액세스할 수 있습니다.
       
       ![격리 복원](./media/quarantine-restore.png)
       
7. 정책이 원활하게 실행되는지 유효성을 검사한 후 정책에서 자동 거버넌스 작업을 사용하여 미래의 누수를 방지하고 정책이 일치하는 경우 관리자 격리의 자동 적용을 방지합니다.

> [!NOTE]
> 파일을 복원할 경우:
> - 원본 공유가 복원되지 않고 기본 폴더 상속이 적용됩니다.
> - 복원된 파일에는 가장 최근 버전만 포함됩니다.
> 
> 
> [!NOTE]
> 격리 폴더 사이트 액세스 관리는 고객의 책임입니다.

#### <a name="how-to-set-up-admin-quarantine"></a>관리자 격리를 설정하는 방법

1. 메타데이터 전용 정책(예: SharePoint Online의 분류 레이블), 기본 DLP 정책(예: 신용 카드 번호를 검색하는 정책) 또는 ICAP 타사 정책(예: Vontu를 검색하는 정책)과 같이 위반을 검색하는 파일 정책을 설정합니다.

2. 격리 위치 설정:
   1. Office 365 SharePoint 또는 비즈니스용 OneDrive의 경우 관리자 격리를 설정하기 전에는 정책의 일부로 파일을 관리자 격리에 넣을 수 없습니다. ![격리 설정](./media/quarantine-warning.png)

      관리자 격리 설정을 지정하려면 [설정] 코그 아래에서 **일반 설정**으로 이동하고, 격리된 파일의 위치 및 해당 파일이 격리될 경우 사용자에게 표시되는 사용자 알림을 제공합니다. 
      ![격리 설정](./media/quarantine-settings.png)

   2. Box의 경우 격리 폴더 위치 및 사용자 메시지를 사용자 지정할 수 없습니다. 폴더 위치는 Box를 Cloud App Security에 연결한 관리자의 드라이브이고 사용자 메시지는 다음과 같습니다. 이 파일은 회사의 보안/규격 정책을 위반할 수 있기 때문에 관리자 드라이브에 격리되었습니다. 도움이 필요하면 IT 관리자에게 문의하세요.



## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
