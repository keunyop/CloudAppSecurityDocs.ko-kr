---
title: 콘텐츠 검사 정책에 Cloud App Security의 RegEx 엔진 사용
description: 이 문서에서는 Cloud App Security 정책에서 패턴 일치에 RegEx를 사용하는 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 12/14/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 07085a2c2e8a27e6e6ad35d9e088a95f8d543522
ms.sourcegitcommit: 8ef0438fa35916c48625ff750cb85e9628d202f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56281120"
---
# <a name="working-with-the-regex-engine"></a>RegEx 엔진 작업

*적용 대상: Microsoft Cloud App Security*
 
이 문서에서는 Cloud App Security 정책에서 패턴 일치에 RegEx를 사용하는 지침을 제공합니다.

## <a name="regular-expressions-in-cloud-app-security"></a>Cloud App Security의 정규식

Microsoft Cloud App Security의 콘텐츠 검사 정책은 패턴 일치에 RegEx를 사용합니다. 파일 정책의 일부로 콘텐츠 검사를 적용할 수 있습니다.

### <a name="testing-regular-expressions"></a>정규식 테스트

정규식을 테스트하기 위해 다음 웹 사이트를 사용할 수 있습니다.  
  
- [https://regexpal.com/](https://regexpal.com/) - **대/소문자 구분 안 함**을 선택해야 합니다.  
  
- [https://regex101.com/](https://regex101.com/) - RegEx에 대한 자세한 분석을 제공합니다.  

### <a name="limitations-of-regular-expressions-in-cloud-app-security"></a>Cloud App Security에서 정규식의 제한 사항

사용자 지정 정규식에는 다음과 같은 제한 사항이 적용됩니다.  
  
- 검색은 항상 대/소문자를 구분하지 않습니다.  

- 허용되는 한정사: {n,m}(여기서 n, m < 10)  
  
- 모든 그룹은 캡처링이 아니어야 합니다(예: (?:xxx)).  
  
     (group) 대신 (?:group)을 사용합니다.  
  
- 허용되지 않는 한정사: *, +, {n,}  
  
     * 대신 {0,9}를 사용합니다.  
  
     + 대신 {1,9}를 사용합니다.  
  
- 허용되지 않는 역참조: \\<number\> 또는 \k\<name>  
  
### <a name="example-expressions"></a>예제 식  

다음 표에서는 예제 식 및 일치 여부를 제공합니다.

|                                                               |                                                               |                                    |
|---------------------------------------------------------------|---------------------------------------------------------------|------------------------------------|
|              <strong>정규식</strong>              |                     <strong>데이터</strong>                     |      <strong>일치 항목</strong>      |
|            Colou?r (?:black&#124;blue&#124;white)             |   검은색<br /><br /> 흰색<br /><br /> 빨간색   | 예<br /><br /> 예<br /><br /> 아니요 |
|           [a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}            | Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com  | 예<br /><br /> 예<br /><br /> 아니요 |
| 20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31) |   2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31    | 예<br /><br /> 예<br /><br /> 아니요 |
|                       d.n't\s{0,10}c.r.                       | Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care | 예<br /><br /> 예<br /><br /> 아니요 |

## <a name="check-out-this-video"></a>이 비디오를 확인해 보세요!

[Regex 엔진 작업](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security-Working-with-the-Regex-Engine)

## <a name="next-steps"></a>다음 단계

[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
