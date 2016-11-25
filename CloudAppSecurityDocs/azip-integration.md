---
title: "Azure Inforamtion Protection 통합 | Microsoft 문서"
description: "이 문서에서는 Cloud App Security에서 Azure Information Protection 태그를 활용하여 조직의 클라우드 응용 프로그램 사용을 상세히 제어하는 방법에 관한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/03/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 759692e7b270d87dc1becf88453d095f2382c411
ms.openlocfilehash: 104dbdbc22d748e924f42c92ba2607e970f03b9e


---

# <a name="azure-information-protection-integration---private-preview"></a>Azure Information Protection 통합 - **비공개 미리 보기**

Cloud App Security를 사용하면 파일을 조사하고 Azure Information Protection 파일 레이블을 기반으로 정책을 설정하여 클라우드에 있는 중요한 데이터를 더 잘 파악하고 제어할 수 있습니다. 그러려면 Cloud App Security에서 콘텐츠 검사를 사용하도록 설정된 파일을 검색하도록 정책을 설정합니다. 또한 Cloud App Security 비공개 미리 보기의 일부로서 기밀 파일과 관련된 활동에 관한 알림을 트리거할 수도 있습니다. Azure Information Protection 통합을 이용하여 다음을 수행할 수 있습니다.
-   클라우드 응용 프로그램을 통해 중요 한 데이터 표시를 계측합니다.
-   정책을 만들고 기밀 데이터를 연결된 클라우드 응용 프로그램에 업로드할 경우 위반 알림을 표시하거나 중요한 데이터를 외부에서 공유하지 못하도록 격리/차단합니다.
-   감사 내역 조사 및 정책을 위반하는 파일 수정 

> [!NOTE] 기본적으로, 콘텐츠 검사를 사용하도록 설정된 파일을 검색하는 파일 정책이 있는 경우에만 파일의 레이블을 검색합니다. 파일 정책 없이 모든 파일에서 레이블을 검색하려면 자동 검색을 사용합니다.

## <a name="terminology-overview"></a>용어 개요
-   Azure Information Protection 분류 레이블- 최종 사용자의 설정에 따라 조직에서 자동으로, 정책을 기반으로 또는 수동으로 추가된 특성입니다.
-   외부- 조직 외부에 있는 사람이 설정한 태그입니다.
-   파일 태그- Cloud App Security에 표시되는 분류 레이블입니다. 이 필드는 파일 표에 있는 각 파일에 대해 표시되며 필터에 사용할 수 있습니다.
-   파일 정책- 파일 필터에 의존하여 클라우드 공급자의 API를 활용하는 넓은 범위의 자동화된 프로세스를 적용할 수 있게 해 주는 규칙 집합입니다.

## <a name="license-and-tenant-creation"></a>라이선스 및 테넌트 만들기
이 기능을 사용하도록 설정하려면 Cloud App Security 라이선스와 Azure Information Protection Premium P1 또는 P2 라이선스가 모두 필요합니다. 두 라이선스가 모두 있으면 Cloud App Security는 즉시 Azure Information Protection 서비스에서 조직 레이블을 동기화합니다.

![샘플 azip 화면](./media/azip-screen.png)

![cas와 azip 비교](./media/cas-compared-azip.png)
     
또한, 기본적으로 파일 정책 하나 이상을 통해 콘텐츠 검사를 통과하는 파일에서도 분류 레이블을 검색합니다.

## <a name="gain-visibility"></a>가시성 확보

각 파일에서 검색된 파일 태그는 파일 서랍에서 확인할 수 있습니다.
**파일** 페이지에서 관련 파일을 클릭하여 파일 태그가 있는지 확인합니다.

![파일 서랍](./media/azip-file-drawer.png)

태그를 클릭하여 자세한 정보를 보거나 전체 태그 목록을 볼 수 있습니다.
 
![태그 목록](./media/azip-tags-list.png)

특정 태그가 지정된 파일을 검색하려면 **파일 태그** 필터를 사용합니다.
 
![파일 태그 필터](./media/azip-file-tags-filter.png)

또는 파일 태그가 하나라도 지정된 파일을 검색하려면:

![파일 태그 모든 필터](./media/azip-file-tags-all-filter.png)

## <a name="enable-automatic-scan"></a>자동 검색 사용
Office 365에서 새 파일의 파일 태그를 자동으로 검색하려면:

1. Office 365에서 **일반 설정** 페이지로 이동합니다.
2. Azure 보안 설정에서 **파일에서 자동으로 Azure Information Protection 분류 레이블 검색**을 선택합니다. 이 설정을 사용하도록 선택하면 파일 정책에 따라 콘텐츠를 검색한 파일만이 아니라 Office 365에 추가된 모든 새 파일에서도 파일 태그를 검색합니다.

![azure information protection 사용](./media/enable-azip.png)
 

## <a name="internal-and-external-tags"></a>내부 및 외부 태그
기본적으로 Cloud App Security에서는 조직에 정의된 분류 레이블과 다른 조직에서 정의된 외부 레이블을 검색합니다. 

무시하려면 **Azure 보안 설정**에서 **다른 테넌트의 Azure Information Protection 분류 레이블 무시**를 선택합니다.
 
![레이블 무시](./media/azip-ignore.png)

> [!Note]
> 테스트 테넌트를 사용하는 경우에는 다른 테넌트에서 받은 파일을 테스트할 수 있도록 외부 분류 레이블을 무시하지 않는 것이 좋을 수도 있습니다.

![cloud app security의 azure information protection 태그](./media/azip-tags-in-cas.png)

## <a name="use-azure-information-protection-tags-to-apply-control"></a>Azure Information Protection 태그를 사용하여 제어 적용
부적절하게 공유된 파일을 찾고 레이블이 지정되어 최근에 수정된 파일을 찾으려면 Cloud App Security에서 파일 정책을 만듭니다. 

**정책 1 - 상자에서 외부 공유된 기밀 데이터:**

1.  파일 정책을 만듭니다.
2.  정책의 이름, 심각도 및 범주를 설정합니다.
3.  다음 필터를 추가하여 상자에서 외부 공유된 모든 기밀 데이터 찾기:

![기밀성 정책](./media/azip-confidentiality-policy.png) 

**정책 2 - 최근에 SharePoint의 Finance 폴더 외부에서 수정된 제한된 데이터:**

1.  파일 정책을 만듭니다.
2.  정책의 이름, 심각도 및 범주를 설정합니다.
3.  다음 필터를 추가하여 최근에 수정된 모든 제한 데이터를 찾고 폴더 선택 옵션에 [Finance 폴더 제외] 추가: 
 
![제한된 데이터 정책](./media/azip-restricted-data-policy.png) 

경고를 설정하거나, 사용자에게 알리거나, 이러한 정책에 즉각적인 조치를 취할 수도 있습니다.
[거버넌스 작업](governance-actions.md)에 대해 자세히 알아보세요.

[Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection)에 대해 자세히 알아보고 Azure Information Protection [빠른 시작 자습서](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial)를 확인하세요.

  

## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  



<!--HONumber=Nov16_HO3-->


