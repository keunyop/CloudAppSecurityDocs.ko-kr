---
title: Cloud App Security에서 콘텐츠 검사를 수행하는 방법
description: 이 문서에서는 클라우드의 데이터에 대해 DLP 콘텐츠 검사를 수행할 때 Cloud App Security에서 수행하는 프로세스에 대해 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 1/6/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c67a387f-8c88-4018-9e80-0fb1455cf768
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: b0fcd13550d62d5ff96462b7d3f9f4a7437c1a44
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568063"
---
# <a name="content-inspection"></a>콘텐츠 검사

*적용 대상: Microsoft Cloud App Security*


콘텐츠 검사를 활성화하면 사전 설정된 식을 사용하거나 다른 사용자 지정된 식을 검색하도록 선택할 수 있습니다.  

정규식을 지정하여 결과에서 파일을 제외할 수 있습니다. 이 옵션은 정책에서 제외하려는 내부 분류 키워드 표준이 있는 경우에 매우 유용합니다.  
   
파일이 위반으로 간주되기 전에 일치하려는 최소 콘텐츠 위반 수를 설정할 수 있습니다. 예를 들어 파일 콘텐츠 내에 10개 이상의 신용 카드 번호가 있는 파일에 대한 경고를 수신하려는 경우 10을 선택할 수 있습니다.  

콘텐츠가 선택한 식에 대해 일치하면 위반 텍스트가 "X" 문자로 바뀝니다. 기본적으로 위반 텍스트는 위반 전후의 100자를 표시하는 컨텍스트에서 마스크되고 표시됩니다. 식의 컨텍스트에서 숫자는 "#" 문자로 바뀌고 Cloud App Security 내에 저장되지 않습니다. **Unmask the last 4 characters of a violation**(위반의 마지막 4자 마스크 해제) 옵션을 선택하여 위반 자체의 마지막 4자를 마스크 해제할 수 있습니다. 정규식에서 검색할 데이터 형식(콘텐츠, 메타데이터 및/또는 파일 이름)을 설정해야 합니다. 기본적으로 콘텐츠 및 메타데이터를 검색합니다. 


## <a name="content-inspection-for-protected-files"></a>보호된 파일에 대한 콘텐츠 검사

관리자는 Cloud App Security를 통해 암호화된 파일의 암호를 해독하고 위반에 대한 해당 콘텐츠를 검색할 수 있는 Cloud App Security 권한을 부여할 수 있습니다.

클라우드 앱 보안에 필요한 권한을 부여하려면 다음 단계를 따릅니다.

1.  **설정**으로 이동한 다음, **Azure Information Protection**으로 이동합니다.
2.  **보호된 파일 검사**를 활성화합니다.
3. 프롬프트에 따라 Azure Active Directory에서 필요한 권한을 허용하세요.
4. 파일별 정책 설정을 구성하여 보호된 파일을 검색할 정책을 결정할 수 있습니다.



## <a name="next-steps"></a>다음 단계
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
