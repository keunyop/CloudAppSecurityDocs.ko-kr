---
title: "파일 | Microsoft 문서"
description: "이 참조 항목에서는 Cloud App Security에서 사용되는 파일 형식 및 파일 필터에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/27/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cadcd6db-05b2-4974-91fe-cfac3d57aecd
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bf862116fb4db1d4a50c25497d72634a97bb3a80
ms.openlocfilehash: 8fca376e5d414192bdb7c99a7741c97ebcaf3892


---

# <a name="files"></a>파일

특정 파일을 찾을 수 있도록 파일 로그를 필터링할 수 있습니다. 기본 필터는 파일 필터링을 시작하기에 좋은 도구를 제공합니다.

 ![기본 파일 로그 필터](media/file-log-filter-basic.png)

더 구체적인 파일로 드릴다운하려면 [고급]을 클릭하여 기본 필터를 확장합니다.

 ![고급 파일 로그 필터](media/file-log-filter-advanced.png)
 
###  <a name="a-namefilefiltersa-file-filters"></a><a name="Filefilters"></a> 파일 필터 
 
Cloud App Security는 20개가 넘는 메타데이터 필터(예: 액세스 수준, 파일 형식)를 기반으로 모든 파일 형식을 모니터링할 수 있습니다. 
 
Cloud App Security의 기본 제공 DLP 엔진은 일반적인 파일 형식(PDF, Office 파일, RTF, HTML, 코드 파일 등)에서 텍스트를 추출하여 콘텐츠 검사를 수행합니다.

다음은 적용할 수 있는 파일 필터 목록입니다. 대부분의 필터는 매우 강력한 정책 만들기 도구를 제공하기 위해 NOT뿐만 아니라 여러 값을 지원합니다.  
> [!NOTE] 
> 파일 정책 필터를 사용하는 경우 **포함**은 쉼표, 점, 공백 또는 밑줄로 구분된 전체 단어만 검색합니다. 따옴표로 묶인 단어는 AND처럼 작동합니다. 예를 들어 **"malware"** **"virus"**를 검색하는 경우 virus_malware_file.exe는 찾지만 malwarevirusfile.exe 및 malware.exe는 찾지 않습니다. 단어 사이의 공백은 OR처럼 작동합니다. 예를 들어 하는 경우처럼 또는 예를 들어 **malware** **virus**를 검색하는 경우 이름에 malware나 virus가 있는 파일을 모두 찾으므로 malware-virus.exe와 virus.exe를 모두 찾습니다.   **같음**은 전체 문자열만 검색합니다. 예를 들어 **malware.exe**를 검색하는 경우 malware.exe를 찾지만 malware.exe.txt는 찾지 않습니다. 

-   액세스 수준 – 공유 액세스 수준(공개, 외부, 내부 또는 전용)입니다.  외부 파일에 대한 자세한 내용은 [일반 설정, 포털 설정](getting-started-with-cloud-app-security.md)을 참조하세요. 내부는 [일반 설정](General-setup.md)에서 설정한 내부 도메인 내의 모든 파일입니다. 외부는 설정한 내부 도메인에 속하지 않는 위치에 저장된 모든 파일입니다. 공유는 공유 수준이 개인보다 위인 파일입니다. 여기에는 내부 공유(내부 도메인 내에서 공유되는 파일), 외부 공유(내부 도메인에 나열되지 않는 도메인에서 공유되는 파일), 링크를 통한 공개(링크를 통해 모든 사용자와 공유할 수 있는 파일) 및 공개(인터넷을 검색하여 찾을 수 있는 파일)가 포함됩니다. 

> [!NOTE]
>  외부 사용자에 의해 연결된 저장소 응용 프로그램에 공유된 파일은 Cloud App Security에서 다음과 같이 처리됩니다.
> - **OneDrive:** OneDrive는 외부 사용자가 OneDrive에 넣는 모든 파일의 소유자로 내부 사용자를 할당합니다. 그러면 이러한 파일은 조직의 소유로 간주되므로 Cloud App Security에서 이러한 파일을 검색하고 OneDrive의 다른 모든 파일에서처럼 정책을 적용합니다.
> - **Google Drive:** Google Drive에서는 이런 파일을 외부 사용자가 소유한 것으로 간주하며, 조직에서 소유하지 않은 파일 및 데이터의 법적 제한 때문에 Cloud App Security에서 이러한 파일에 액세스할 수 없습니다.
> - **Box:** Box에서는 외부에서 소유한 파일을 개인 정보로 간주하므로 Box 전역 관리자가 파일의 내용을 볼 수 없습니다. 이러한 이유로 Cloud App Security에서 이러한 파일에 액세스할 수 없습니다. 
> - **Dropbox:** Dropbox에서는 외부에서 소유한 파일을 개인 정보로 간주하므로 Box 전역 관리자가 파일의 내용을 볼 수 없습니다. 이러한 이유로 Cloud App Security에서 이러한 파일에 액세스할 수 없습니다.

-   앱 – 해당 앱 내의 파일만 검색합니다.  
  
-   협력자 - 특정 협력자 그룹을 포함/제외합니다.  
  
    -   도메인 중 하나 - 이 도메인의 사용자 중 하나가 파일에 액세스할 수 있는 경우입니다.  
  
    -   전체 도메인 – 전체 도메인이 파일에 액세스할 수 있는 경우입니다.  
  
    -   그룹 – 특정 그룹이 파일에 액세스할 수 있는 경우입니다. Active Directory 또는 클라우드 앱에서 그룹을 가져오거나 서비스에서 수동으로 만들 수 있습니다.  
  
    -   사용자 - 파일에 액세스할 수 있는 특정 사용자 집합입니다.  
  
-   만든 날짜 – 파일을 만든 시간입니다. 필터는 이전/이후 날짜와 날짜 범위를 지원합니다.  
  
-   확장 - 특정 파일 확장명에 집중합니다(예: 실행 파일(exe)인 모든 파일).  
  
-   파일 ID - 특정 파일 ID를 검색합니다. 소유자/위치/이름을 사용하지 않고 중요한 특정 파일을 추적할 수 있는 고급 기능입니다.  
  
-   파일 이름 - 클라우드 앱에 정의된 이름의 파일 이름 또는 하위 문자열입니다(예: 이름에 암호가 포함된 모든 파일).   
  
-   파일 태그 - Azure Information Protection에 의해 설정된 특정 태그를 사용하여 파일을 검색합니다. 그러려면 Azure Information Protection과 통합해야 합니다.

-   파일 형식 – Cloud App Security는 서비스에서 받은 MIME 형식을 모두 사용하고 파일을 검색하여 실제 파일 형식을 확인합니다. 이 검색은 데이터 검색과 관련된 파일(문서, 이미지, 프레젠테이션, 스프레드시트, 텍스트 및 zip/보관 파일)에 대해 수행됩니다. 필터는 파일/폴더 형식을 기준으로 작동합니다(예: ...인 모든 폴더 또는 ...인 모든 스프레드시트 파일).


 ![policy_file 필터 휴지통](./media/policy_file-filters-trash.png "policy_file filters trash")  

  
-   휴지통 – 휴지통 폴더의 파일을 제외/포함합니다. 이러한 파일도 여전히 공유될 수 있으며 위험을 발생시킵니다.  
  
-   마지막으로 수정한 날짜 - 파일 수정 시간입니다. 필터는 이전/이후 날짜, 날짜 범위 및 상대 시간 식을 지원합니다(예: 지난 6개월 동안 수정되지 않은 모든 파일).  

-   일치 정책 - 활성 Cloud App Security 정책과 일치하는 파일입니다.

-   MIME 형식 – 파일 MIME 형식 검사이며 일반 텍스트를 수락합니다.  
  
-   소유자 - 특정 파일 소유자를 포함/제외합니다(예: rogue_employee_#100이 공유하는 모든 파일 추적).  
  
-   소유자 OU – 특정 조직 그룹에 속하는 파일 소유자를 포함/제외합니다(예: EMEA_marketing이 공유하는 파일을 제외한 모든 공용 파일).  
  
-   부모 폴더 – 부모 폴더에 따라 포함/제외합니다(예: 이 폴더의 파일을 제외하고 공개적으로 공유된 모든 파일).  
  
-   격리 – 서비스에서 격리된 파일입니다(예: 격리된 모든 파일 표시).  
  
**적용 대상** 필터를 모든 파일, 선택한 폴더 또는 선택한 폴더를 제외한 모든 파일로 설정하여 특정 파일에 대해 실행할 정책을 설정한 다음 관련된 폴더나 파일을 선택할 수도 있습니다.  
  
![필터에 적용](./media/apply-to-filter.png "apply to filter")  
  
## <a name="working-with-the-file-drawer"></a>파일 서랍 사용

파일 로그에서 파일 자체를 클릭하여 각 파일에 관한 자세한 정보를 볼 수 있습니다. 그러면 파일에서 수행할 다음 추가 작업을 제공하는 파일 서랍이 열립니다.

- URL: 파일 위치로 이동합니다.
- 파일 식별자: 파일 식별자를 클릭하면 파일 ID, 암호화 키를 비롯한 파일에 관한 원시 데이터 정보가 포함된 팝업이 열립니다.
- 소유자: 이 파일의 소유자에 대한 사용자 페이지를 보려면 소유자를 클릭합니다.
- 일치 정책: 이 파일과 일치하는 정책의 목록을 보려면 일치 정책 링크를 클릭합니다.
- 분류 레이블: 이 파일에 있는 Azure Information Protection 분류 레이블 목록을 보려면 분류 레이블을 클릭합니다. 그런 다음 이 레이블과 일치하는 모든 파일을 기준으로 필터링할 수 있습니다.    

![파일 서랍](./media/file-drawer.png "File drawer")  
  
사용할 수 있는 거버넌스 작업 목록은 [파일 거버넌스 작업](governance-actions.md#file-governance-actions)을 참조하세요.

## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


