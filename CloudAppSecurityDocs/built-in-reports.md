---
title: 보고서 생성 - Microsoft Cloud App Security | Microsoft Docs
description: 이 문서에서는 Microsoft Cloud App Security에서 데이터 관리 보고서를 생성하기 위한 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 0dcc3c35-f787-4822-84c6-d4dff897dd6c
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 10db997cbd537587b3571560207680db6b73b4a6
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53176851"
---
# <a name="generate-data-management-reports"></a>데이터 관리 보고서 생성

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security를 사용하면 클라우드 앱의 파일 개요를 제공하는 보고서를 생성할 수 있습니다.

보고서를 생성하려면

1. **파일**로 이동합니다. 
2. 오른쪽 위 모서리에서 점 세 개를 클릭하고 **데이터 관리 보고서**에서 다음 보고서 중 하나를 선택합니다.

 ![보고서](./media/reports.png)

## <a name="data-sharing-overview"></a>데이터 공유 개요 

이 보고서는 각 클라우드 앱에 저장된 파일 수를 액세스 권한별로 나열합니다. 액세스하기 쉽고 어디에서나 이용 가능하므로 클라우드 앱에서는 파일을 쉽게 공유할 수 있습니다. **비공개 파일**은 소유자를 제외하고 다른 어떤 누구와도 공유되지 않습니다. 파일이 공유된 경우 Cloud App Security는 다음 네 가지 유형의 상태를 구별합니다.
- **공개적으로 공유된(인터넷)** 파일은 검색 엔진 결과를 통해서도 인증 없이 액세스할 수 있는 파일입니다.
 - **공개적으로 공유된** 파일은 링크를 사용하여 인증 없이 액세스할 수 있는 파일입니다.
 - **외부와 공유된** 파일은 조직 외부의 사용자가 클라우드 앱에 인증되면 액세스할 수 있는 파일입니다.
- **내부적으로 공유된** 파일은 조직의 모든 또는 일부 사용자가 액세스할 수 있는 파일입니다.

## <a name="outbound-sharing-by-domain"></a>도메인별 아웃바운드 공유

이 보고서는 직원이 회사 파일을 공유한 도메인을 보여 줍니다. 각 도메인에 대한 보고서는 사용자가 해당 도메인과 파일을 공유하고 있는지 보여 줍니다. 이 보고서는 또한 어떤 파일이 공유되고 공동 작업자 파일이 누구와 공유되는지 보여줍니다. 이러한 도메인과의 공유를 관리하는 것이 좋습니다. 각 관련 앱의 앱 페이지에 있는 파일 탭을 통해 공유를 관리할 수 있습니다.

## <a name="owners-of-shared-files"></a>공유 파일의 소유자

이 보고서는 외부와 회사 파일을 공유하는 사용자를 보여 줍니다. 외부와 공유된 파일은 특정 외부 공동 작업자와 공유되는 파일입니다. 공개적으로 공유된 파일은 인터넷에서 누구나 비공개 링크를 통해 액세스할 수 있습니다. 이러한 파일은 명시적으로 링크를 가진 찾을 수 있습니다. 공개적으로 공유된 파일(인터넷)은 인터넷에서 누구든지 검색 엔진 결과 등을 통해 액세스할 수 있습니다. 너무 많은 파일을 공유하는 사용자가 있다면 그 이유를 조사하는 것이 좋습니다. 파일 탭을 사용하여 조사한 다음, 이러한 사용자에게 연락하여 외부 공유 사용에 대해 자세히 파악할 수 있습니다.


  
## <a name="next-steps"></a>다음 단계 
[제어](control.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  