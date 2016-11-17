---
title: "Cloud Discovery 변칙 검색 정책 | Microsoft 문서"
description: "이 항목에서는 Cloud Discovery 변칙 검색 정책을 사용하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 400741713d40422a3b1c7680663a572d18e9c692
ms.openlocfilehash: 132b4d296b26dd187418734b40d08ecb243692da


---

# <a name="cloud-discovery-anomaly-detection-policy"></a>클라우드 검색 변칙 검색 정책
이 문서에서는 정책에 대한 참조 정보를 제공하며 각 정책에 대해 구성할 수 있는 필드와 각 정책 형식에 대해 설명합니다.  
  
## <a name="cloud-discovery-anomaly-detection-policy-reference"></a>클라우드 검색 변칙 검색 정책 참조  
클라우드 검색 변칙 검색 정책을 사용하면 클라우드 응용 프로그램 사용의 비정상적인 증가에 대한 지속적인 모니터링을 설정 및 구성할 수 있습니다. 각 클라우드 응용 프로그램에 대해 다운로드한 데이터, 업로드한 데이터, 트랜잭션 수 및 사용자 수의 증가가 고려됩니다. 과거 사용에서 확인된 응용 프로그램의 일반적인 사용 패턴과 각 증가를 비교합니다. 가장 극단적인 증가는 보안 경고를 트리거합니다.  
  
각 정책은 다음 부분으로 구성됩니다.  
  
-   필터 – 응용 프로그램 필터, 선택한 데이터 뷰, 선택한 시작 날짜를 기준으로 응용 프로그램 사용을 선택적으로 모니터링할 수 있습니다.  
  
-   민감도 – 정책에서 트리거할 경고 수를 설정할 수 있습니다.  
  
### <a name="activity-filters"></a>활동 필터  
활동 필터 목록은 [활동](activity-filters.md)을 참조하세요.  
  
### <a name="apply-to"></a>적용 대상  
모니터링되는 사용을 다음 두 가지 방법으로 필터링할 수 있습니다.  
  
-   데이터 뷰 – 모든 데이터 뷰를 모니터링할지(기본값) 또는 모니터링할 특정 데이터 뷰를 선택할지를 선택합니다.  
  
    -   **모든 데이터 뷰**를 선택하는 경우 모든 데이터 뷰에서 확인된 일반적인 사용 패턴과 각 사용 증가를 비교합니다.  
  
    -   특정 데이터 뷰를 선택하는 경우 증가가 관찰된 데이터 뷰에서 확인된 일반적인 사용 패턴과 각 사용 증가를 비교합니다.  
  
-   사용자 및 IP 주소 - 모든 클라우드 응용 프로그램 사용은 사용자, IP 주소 또는 둘 다와 연결됩니다.  
  
    -   **사용자**를 선택하면 IP 주소와 응용 프로그램 사용 연결이 무시됩니다(있는 경우).  
  
    -   **IP 주소**를 선택하면 사용자와 응용 프로그램 사용 연결이 무시됩니다(있는 경우).  
  
    -   **사용자 및 IP 주소**를 선택하면 두 연결이 모두 고려되지만 사용자와 IP 주소 간에 밀접한 상관 관계가 있는 경우 중복 경고가 생성될 수 있습니다.  
  
날짜 후에 발생하는 의심스러운 활동에 대해서만 경고를 발생시키고 선택한 날짜 전의 응용 프로그램 사용 증가는 무시됩니다. 그러나 일반적인 사용 패턴을 정하기 위해 선택한 날짜 전의 활동이 확인됩니다.  
  
### <a name="sensitivity"></a>민감도  
정책에 따라 트리거되는 경고 수를 제어하는 방법에는 다음 두 가지가 있습니다.  
  
-   민감도 슬라이더 – 매주 1,000명당 트리거할 경고 수를 선택합니다. 위험이 가장 높은 활동의 경고가 트리거됩니다.  
  
-   일일 경고 제한 – 하루에 발생하는 경고 수를 제한합니다.  
  
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


