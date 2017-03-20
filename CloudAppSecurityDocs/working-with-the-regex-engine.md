---
title: "콘텐츠 검사 정책에 RegEx 엔진 사용 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security 정책에서 패턴 일치에 RegEx를 사용하는 지침을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/12/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c386cbbdadaf97297e6d876cdac9f7d3e2142b73
ms.sourcegitcommit: b840b945b270e616560f565bcc6590dd68ad5ebd
translationtype: HT
---
# <a name="working-with-the-regex-engine"></a>RegEx 엔진 작업
 
Cloud App Security의 콘텐츠 검사 정책은 패턴 일치에 RegEx를 활용합니다. 파일 정책의 일부로 콘텐츠 검사를 적용할 수 있습니다. 정규식을 테스트하려면 다음 웹 사이트를 사용할 수 있습니다.  
  
-   [http://regexpal.com/](http://regexpal.com/)  
  
     **대/소문자 구분 안 함**을 선택해야 합니다.  
  
-   [https://regex101.com/](https://regex101.com/)  
  
     정규식에 대한 자세한 분석을 제공합니다.  
  
사용자 지정 정규식에는 다음과 같은 제한 사항이 적용됩니다.  
  
-   검색은 항상 대/소문자를 구분하지 않습니다.  
   
-   허용되는 한정사: {n,m}(여기서 n, m < 10)  
  
-   모든 그룹은 캡처링이 아니어야 합니다(예: (?:xxx)).  
  
     (group) 대신 (?:group)을 사용합니다.  
  
-   허용되지 않는 한정사: *, +, {n,}  
  
     * 대신 {0,9}를 사용합니다.  
  
     + 대신 {1,9}를 사용합니다.  
  
-   허용되지 않는 역참조: \\<number\> 또는 \k\<name>  
  
예제 식  
  
||||  
|-|-|-|  
|**정규식**|**데이터**|**일치 항목**|  
|Colou?r (?:black&#124;blue&#124;white)|검은색<br /><br /> 흰색<br /><br /> 빨간색|예<br /><br /> 예<br /><br /> 아니요|  
|[a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}|Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com|예<br /><br /> 예<br /><br /> 아니요|  
|20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31)|2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31|예<br /><br /> 예<br /><br /> 아니요|  
|d.n't\s{0,10}c.r.|Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care|예<br /><br /> 예<br /><br /> 아니요|  
 

## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  