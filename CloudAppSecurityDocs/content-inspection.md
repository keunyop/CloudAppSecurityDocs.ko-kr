---
title: Cloud App Security에서 콘텐츠 검사를 수행하는 방법 | Microsoft 문서
description: 이 문서에서는 클라우드의 데이터에 대해 DLP 콘텐츠 검사를 수행할 때 Cloud App Security에서 수행하는 프로세스에 대해 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/11/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0f4a97d719c409987bc5b3df268338b562c3da67
ms.sourcegitcommit: 3177ffcbdabbddc6c758e9a1994fb21fde939ffc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35259582"
---
*적용 대상: Microsoft Cloud App Security*



# <a name="built-in-content-inspection"></a>기본 제공 콘텐츠 검사

이 문서에서는 클라우드의 데이터에 대해 기본 제공 DLP 콘텐츠 검사를 실행할 때 Microsoft Cloud App Security에서 수행하는 프로세스를 설명합니다. 


Cloud App Security 콘텐츠 검사는 다음과 같이 작동합니다.
1. 먼저, Cloud App Security에서 새롭거나 변경된 것으로 감지되는 드라이브 및 이벤트에 대해 NRT(근 실시간) 검색을 수행합니다.
2. 이 작업이 완료되면 Cloud App Security에서 모든 드라이브의 모든 관련 파일에 대해 연속 검색을 수행합니다.  

NRT 검색과 연속 검색의 파일 모두 검사를 위해 큐에 추가됩니다. 검색 큐에서 파일의 순서는 드라이브의 검색 및 파일에 대한 활동에 따라 설정됩니다. 파일은 파일 메타데이터가 지원되는 MIME 형식으로 표시되는 경우에만 검색됩니다. 이 검색은 데이터 검색과 관련된 파일(문서, 이미지, 프레젠테이션, 스프레드시트, 텍스트 및 zip/보관 파일)에 대해 수행됩니다.  

파일을 검색한 후에는 다음 작업이 수행됩니다.

1. Cloud App Security에서 콘텐츠 자체가 아니라 메타데이터와 관련된 모든 사용자 지정 정책을 적용합니다. 예를 들어 파일이 20MB 이상인 경우 경고하는 정책 또는 docx 파일이 OneDrive에 저장되는 경우 경고하는 정책이 있습니다. 

2. 콘텐츠 검사가 필요한 정책이 있고 파일이 콘텐츠 검사 조건을 충족하는 경우 콘텐츠는 검사를 위해 큐에 대기됩니다. 큐 길이는 테넌트의 크기 및 검색이 필요한 파일의 수에 따라 달라집니다. 

3. 이제 **조사** > **파일**로 이동하고 파일을 클릭하여 콘텐츠 검사의 상태를 확인할 수 있습니다. 파일의 세부 정보와 함께 열리는 파일 서랍의 **콘텐츠 검사 상태**에 **완료됨**, **보류 중**, **해당 없음**(파일 형식이 지원되지 않는 경우) 또는 오류 메시지가 표시됩니다. 콘텐츠 검색 오류 메시지에 대한 자세한 내용은 [콘텐츠 검사 문제 해결](troubleshooting-content-inspection.md)을 참조하세요.

> [!NOTE]
> 검색 상태에 대시가 표시되는 경우 검색할 파일이 큐에 대기 되지 않은 것입니다. 콘텐츠 검사 정책을 설정하는 방법에 대한 자세한 내용은 [파일 정책](data-protection-policies.md)을 참조하세요.

기본 제공 콘텐츠 검사 검색 정책에서는 다음을 검색할 수 있습니다.

- 메일 주소 
- 신용 카드 번호 
  - 모든 신용 카드 회사(Visa, MasterCard, American Express, Diners Club, Discover, JCB, Dankort, UnionPay) 
  - 구분 기호 - 공백, 점 또는 대시
  - 이 검색에는 Luhn 유효성 검사도 포함됩니다.
- SWIFT 코드
- 국제 여권 번호
- 운전 면허 번호
- 날짜
- 은행 ABA 라우팅 지점 번호
- 은행 식별 코드
- HIPAA HICN 건강 보험 청구 번호
- HIPAA NPI 국가 공급자 식별 번호
- PHI 전체 이름 및 생년월일
- 캘리포니아 ID 또는 운전 면허 번호
- 운전 면허 번호
- 집 주소
- 여권 카드
- 사회 보장 번호

## <a name="supported-languages"></a>지원되는 언어

Cloud App Security 콘텐츠 검사 엔진:
-   모든 유니코드 문자 지원
-   1, 000개가 넘는 파일 형식 포함
-   여러 언어를 지원하며 특히, 유니코드 문자 집합을 사용하는 파일을 지원합니다. 해당 언어를 포괄할 정책을 정의해야 합니다. 예를 들어 키워드를 찾을 경우 사용하려는 언어 전체에 키워드를 포함해야 합니다.
-   중국어 GB2312와 같이 비유니코드 인코딩을 사용하는 텍스트 기반 파일 형식에서, 유니코드 중국어 키워드에 대한 비교는 예상대로 작동하지 않습니다.
-   타사 라이브러리를 사용하는 파일 형식의 경우 문자열과 단어의 일치가 예상대로 작동하지 않을 수 있습니다. 이는 콘텐츠 검사 시 언어와 문자 집합에 대해 Java 문자열을 반환하는 타사 라이브러리 파일을 사용하는 파일(예: 이진 파일 형식)에서 매우 흔한 일입니다.



## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  