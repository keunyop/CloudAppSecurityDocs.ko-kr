---
title: Cloud App Security에서 검색된 앱 사용 | Microsoft Docs
description: 이 항목에서는 Cloud App Security에서 위험한 클라우드 검색 앱을 식별 및 해결하기 위한 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/6/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 645fd8c7-06d0-4f93-a85c-2976e7b3766d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9c9cae44e8ecbd3856495723f951c050fa8f50e3
ms.sourcegitcommit: a97e6d93124433547149fd8a642fcb77e02a75f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39519060"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="working-with-discovered-apps"></a>검색된 앱 사용

## <a name="review-the-cloud-discovery-dashboard"></a>Cloud Discovery 대시보드 검토

Cloud Discovery 대시보드는 조직에서 클라우드 앱이 어떻게 사용되는지를 효과적으로 파악할 수 있도록 설계되었습니다. 이 대시보드에서는 사용되고 있는 앱의 종류, 미해결 경고 및 조직에서 앱의 위험 수준을 한눈에 파악할 수 있습니다. 또한 최고의 앱 사용자를 확인할 수 있으며 앱 본사 위치 지도를 제공합니다. Cloud Discovery 대시보드는 가장 관심 있는 항목에 따라 데이터를 필터링할 수 있는 많은 옵션을 제공하여 특정 뷰를 생성할 수 있으며, 이해하기 쉬운 그래픽을 통해 한눈에 볼 수 있는 전체 사진을 제공합니다.

![cloud discovery 대시보드](./media/cloud-discovery-dashboard.png)

Cloud Discovery 앱을 일반적으로 살펴보기 위해 가장 먼저 해야 할 일은 Cloud Discovery 대시보드를 보고 다음 사항을 검토하는 것입니다.
 
1. 먼저 **개략적인 사용 개요**에서 조직의 전반적인 클라우드 앱 사용을 살펴봅니다.

2. 그런 다음 한 수준 아래에서 다양한 각 사용 매개 변수에 대해 조직에서 사용되고 있는 **상위 범주**와 사용 권한 앱의 사용량을 확인합니다.

3. **검색된 앱** 위젯에서 특정 범주의 앱을 훨씬 더 심층적으로 살펴보고 확인합니다.

4. **상위 사용자와 원본 IP 주소**를 확인하면 조직에서 어떤 사용자가 클라우드 앱을 가장 많이 사용하는지 파악할 수 있습니다.
5. 검색된 앱이 **앱 본사 지도**에서 지리적 위치(HQ)에 따라 어떻게 분산되는지 확인합니다.

6. 마지막으로 **앱 위험 개요**에서 검색된 앱의 위험 점수를 검토하고 **검색 경고 상태**를 확인하여 조사해야 하는 미해결 경고 수를 확인합니다.

## <a name="deep-dive-into-discovered-apps"></a>검색된 앱 심층 분석
Cloud Discovery에서 제공된 데이터를 심층 분석하려면 필터를 사용하여 위험한 앱과 일반적으로 사용되는 앱을 검토합니다.


예를 들어 일반적으로 사용되는 위험한 클라우드 저장소 및 공동 작업 앱을 식별하려면 검색된 앱 페이지를 사용하여 원하는 앱을 필터링합니다. 나중에 다음과 같이 앱의 [사용 권한을 취소하거나 앱을 차단](governance-discovery.md)할 수 있습니다.

**검색된 앱** 페이지의 **범주별로 찾아보기**에서 **클라우드 저장소** 및 **공동 작업**을 둘 다 선택합니다. 그다음에 고급 필터를 사용하고 **Compliance risk factor**(규격 위험 요인)를 **SOC 2**가 **False**와 같게 설정하고, **사용량** > **사용자**를 50명보다 크게 설정하고, **사용량** > **트랜잭션**을 100보다 크게 설정하고, **보안 위험 요인** > **미사용 데이터 암호화**를 **False**로 설정하고 나서, **위험 점수**를 6보다 작게 설정합니다.

![검색된 앱 필터](./media/discovered-app-filters.png)

결과가 필터링된 후 [대량 작업] 확인란을 사용하여 하나의 작업으로 모든 앱의 사용 권한을 취소하는 방식으로 앱의 [사용 권한을 취소하거나 앱을 차단](governance-discovery.md)할 수 있습니다. 사용 권한이 취소된 후 차단 스크립트를 사용하여 앱이 환경에서 사용되지 않도록 차단할 수 있습니다.

Cloud Discovery를 사용하면 조직의 클라우드 사용을 더 자세히 파악하고, 검색한 하위 도메인을 조사하여 사용 중인 특정 인스턴스를 식별할 수 있습니다.
     
예를 들어 서로 다른 SharePoint 사이트를 구분할 수 있습니다.

Cloud Discovery는 대상 URL 데이터를 포함하는 방화벽 및 프록시에서만 지원됩니다. [지원되는 방화벽 및 프록시](set-up-cloud-discovery.md#supported-firewalls-and-proxies)에서 지원되는 어플라이언스 목록을 참조하세요.

 ![하위 도메인 정보](./media/discovery-domains.png) 

## <a name="generate-cloud-discovery-executive-report"></a>Cloud Discovery 임원 보고서 생성

조직에서 Shadow IT를 사용하는 개요를 가져오는 가장 좋은 방법은 Cloud Discovery 임원 보고서를 생성하는 것입니다. 이 보고서는 잠재적인 상위 위험을 식별하고 위험을 해결할 때까지 완화하고 관리하는 워크플로를 계획할 수 있습니다.

Cloud Discovery 임원 보고서를 생성하려면: 

Cloud Discovery 대시보드에서 메뉴의 오른쪽 위 모서리에서 줄임표를 클릭하고 **Cloud Discovery 생성 임원 보고서**를 선택합니다.

## <a name="exclude-entities"></a>엔터티 제외  
특히 노이즈가 많고 흥미 없는 시스템 사용자 또는 IP 주소나 관련 없는 앱이 있는 경우 분석되는 클라우드 검색 데이터에서 해당 데이터를 제외하는 것이 좋습니다. 예를 들어 127.0.0.1 또는 로컬 호스트에서 발생하는 모든 정보를 제외할 수 있습니다.  
  
제외 항목을 만들려면  
  
1.  포털의 설정 아이콘에서 **클라우드 검색 설정**을 선택합니다.  
  
2.  **엔터티 제외** 탭을 클릭합니다.  
  
3.  **제외된 사용자** 또는 **제외된 IP 주소** 탭을 선택하고 **사용자 추가** 또는 **IP 주소 추가** 단추를 클릭합니다.  
  
4.  사용자 별칭 또는 IP 주소를 추가합니다. 사용자 또는 IP 주소가 제외된 이유에 대한 정보를 추가하는 것이 좋습니다.  
  
     ![사용자 제외](./media/exclude-user.png "사용자 제외")  
  
## <a name="manage-continuous-reports"></a>연속 보고서 관리  
사용자 지정 연속 보고서는 조직의 Cloud Discovery 로그 데이터를 모니터링할 때 더 많은 세분성을 제공합니다. 사용자 지정 보고서를 만들어 특정 지리적 위치, 네트워크 및 사이트 또는 조직 구성 단위를 기준으로 필터링할 수 있습니다. 기본적으로 다음과 같은 보고서만 Cloud Discovery 보고서 선택기에 표시 됩니다.  
  
-  **전역 보고서**는 로그에 포함한 모든 데이터 원본의 모든 정보를 포털에서 통합합니다.  
  
- **데이터 원본 특정 보고서**는 특정 데이터 원본의 정보만 표시합니다.  
  
새 연속 보고서를 만들려면  
  
1.  포털의 설정 아이콘에서 **클라우드 검색 설정**을 선택합니다.  
  
2.  **연속 보고서 관리** 탭을 클릭합니다.  
  
3.  **보고서 만들기** 단추를 클릭합니다.  
  
4.  보고서 이름을 입력합니다.  
  
5.  포함할 데이터 원본을 선택합니다(모두 또는 특정).  
  
6.  데이터에 대해 원하는 필터를 설정합니다. 이러한 필터는 **조직 구성 단위**, **IP 주소 태그** 또는 **IP 주소 범위**가 될 수 있습니다. IP 주소 태그 및 IP 주소 범위 작업에 대한 자세한 내용은 [요구에 따라 데이터 구성](ip-tags.md)을 참조하세요.  
  
    ![사용자 지정 연속 보고서 만들기](./media/create-custom-continuous-report.png) 

> [!NOTE]
> 모든 사용자 지정 보고서는 최대 1GB의 압축되지 않은 데이터로 제한됩니다. 데이터가 1GB를 초과하면 데이터의 처음 1GB를 보고서로 내보냅니다.


## <a name="deleting-cloud-discovery-data"></a>클라우드 검색 데이터 삭제  
다양한 이유로 클라우드 검색 데이터를 삭제할 수 있습니다. 다음과 같은 경우 삭제하는 것이 좋습니다.  
  
-   로그 파일을 수동으로 업로드했으며 시스템을 새 로그 파일로 업데이트하기 전에 오랜 시간이 경과하여 이전 데이터가 결과에 영향을 주지 않도록 하려는 경우  
  
-   새 사용자 지정 데이터 뷰를 설정하면 해당 시점 이후의 새 데이터에만 적용되므로 이전 데이터를 지운 다음 로그 파일을 다시 업로드하여 사용자 지정 데이터 뷰가 로그 파일 데이터에서 이벤트를 선택할 수 있게 하는 것이 좋습니다.  
  
-   많은 사용자 또는 IP 주소가 일정 시간 동안 오프라인 상태였다가 최근에 작업을 다시 시작한 경우 해당 활동이 비정상으로 식별되고 많은 가양성 위반이 표시될 수 있습니다.  
  
클라우드 검색 데이터를 삭제하려면  
  
1. 포털의 설정 아이콘에서 **클라우드 검색 설정**을 선택합니다.  
  
2. **데이터 삭제** 탭을 클릭합니다.  
  
    계속하기 전에 데이터를 삭제할 것인지 확인하는 것이 좋습니다. 이 작업은 실행 취소할 수 없으며 시스템의 **모든** Cloud Discovery 데이터가 삭제됩니다.  
  
3. **삭제** 단추를 클릭합니다.  
  
    ![데이터 삭제](./media/delete-data.png "데이터 삭제")  
  
   > [!NOTE]  
   >  삭제 프로세스는 몇 분 정도 걸리며 즉시 적용되지 않습니다.  




## <a name="see-also"></a>참고 항목
 
[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[연속 보고서에 대한 자동 로그 업로드 구성](configure-automatic-log-upload-for-continuous-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)

