---
title: "활동 | Microsoft 문서"
description: "이 항목에서는 활동 정책에 적용할 수 있는 활동, 필터 및 일치 매개 변수 목록을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 401801da8a4439b3dc0cf5c2f150c72e169a6d16


---

# <a name="activities"></a>활동
다음은 적용할 수 있는 활동 필터 목록입니다. 대부분의 필터는 매우 강력한 정책 만들기 도구를 제공하기 위해 NOT뿐만 아니라 여러 값을 지원합니다.  
  
-   활동 - 모든 파일 업로드, 새로운 장치에서 로그인, 실패한 로그인 등 특정 활동만 검색합니다.  
  
-   활동 ID - 해당 ID로 특정 활동만 검색합니다. 이 필터는 MCAS를 SIEM에 연결할 때(SIEM 에이전트 사용) 매우 유용하며, MCAS 포털 내에서 경고를 자세히 조사할 수 있습니다.  
  
-   관리 활동 – 관리 활동만 검색합니다.  
  
-   가장된 활동 - 다른 사용자의 이름으로 수행된 활동만 검색합니다.  
  
-   앱 - 특정 앱 내의 활동만 검색합니다.  
  
-   날짜 - 활동이 발생한 날짜입니다. 필터는 이전/이후 날짜와 날짜 범위를 지원합니다.  
  
-   사용자 - 활동을 수행한 사용자입니다. 특정 사용자 없이 활동을 필터링하려면 '설정되지 않음' 연산자를 사용할 수 있습니다.  
  
     ![활동 ref1](./media/activity-ref1.png "activity ref1")  
  
-   IP 주소 - 활동이 수행된 IP 주소입니다.  
  
-   IP 범주 - 활동을 수행한 IP 주소 범주입니다(예: 관리 IP 주소 범위의 모든 활동). IP 범주에 대한 자세한 내용은 [요구에 따라 데이터 구성](general-setup.md#IPtagsandRanges)을 참조하세요.  
  
-   IP 태그 - 활동을 수행한 IP 주소의 태그입니다(예: 익명 프록시 IP 주소의 모든 활동). IP 태그에 대한 자세한 내용은 [요구에 따라 데이터 구성](general-setup.md#IPtagsandRanges)을 참조하세요.  
  
-   위치 – 활동을 수행한 국가입니다.  
  
-   등록된 ISP – 활동을 수행한 ISP입니다.  
  
     ![활동 정책 ref2](./media/activity-policy-ref2.png "activity policy ref2")  
  
-   장치 유형 - 특정 장치 유형을 사용하여 수행된 활동만 검색합니다(예: 모바일 장치의 모든 활동).  
  
-   사용자 에이전트 – 활동을 수행한 사용자 에이전트입니다.  
  
-   사용자 에이전트 태그 – 기본 제공 사용자 에이전트 태그입니다(예: 오래된 브라우저 또는 오래된 운영 체제의 모든 활동).  
  
-   사용자 조직 – 활동을 수행한 사용자의 조직 구성 단위(예: EMEA_marketing 사용자가 수행한 모든 활동).  
  
- 대상 개체 - 특정 파일을 선택할 수 있습니다. 

-   사용자 그룹 – MCAS가 클라우드 앱에서 자동으로 가져온 특정 사용자 그룹입니다(예: Office 365 관리자가 수행한 모든 활동).  
  
-   설명 – 활동 설명의 특정 키워드입니다(예: 설명에 **user** 문자열이 포함된 모든 활동).  
  
-   일치 정책 – 포털에 설정된 특정 정책에서 일치하는 활동을 검색합니다.  
  
     ![활동 정책 ref3](./media/activity-policy-ref3.png "Activity policy ref3")  
  
## <a name="activity-match-parameters"></a>활동 일치 매개 변수  
정책과 일치하는 데 필요한 활동 반복량을 지정합니다(예: 사용자가 2분 시간 프레임 내에 로그인 시도를 10회 실패할 경우 경고하는 정책 설정).  
기본 설정 **활동 일치 매개 변수**는 모든 활동 필터를 충족하는 모든 단일 활동에 대해 일치를 발생시킵니다.   
**반복 활동**을 사용하여 반복 활동 수와 활동이 계산되는 시간 프레임 기간을 설정하고 동일한 사용자가 동일한 클라우드 앱에서 모든 활동을 수행하도록 지정할 수 있습니다.  
  
### <a name="actions"></a>작업  
알림  
  
-   경고 - 심각도 수준에 따라 시스템에서 경고가 트리거되고 메일 및 텍스트 메시지를 통해 전파될 수 있습니다.  
  
-   사용자 메일 알림 - 메일 메시지를 사용자 지정할 수 있으며 위반하는 모든 파일 소유자에게 전송됩니다.  
  
-   참조 관리자 - 사용자 디렉터리 통합에 따라 정책을 위반하는 사용자의 관리자에게 메일 알림을 보낼 수도 있습니다.  
  
-   추가 사용자에게 알림 - 이러한 알림을 받을 특정 메일 주소 목록입니다.  
  
앱의 거버넌스 작업  
  
-   앱별로 세부적인 작업을 적용할 수 있습니다. 특정 작업은 앱 용어에 따라 달라집니다.  
  
-   사용자 일시 중단 – 응용 프로그램에서 사용자를 일시 중단합니다.  
  
-   암호 철회 – 사용자 암호를 해지하고 다음 로그인 시 새 암호를 설정하도록 강제합니다.  
  
     ![활동 정책 ref6](./media/activity-policy-ref6.png "activity policy ref6")  
  
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


