---
title: Microsoft Cloud App Security에서 보고서를 생성하는 방법 | Microsoft 문서
description: 이 항목에서는 Microsoft Cloud App Security에서 데이터 관리 보고서를 생성하기 위한 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/10/2018
ms.topic: article
ms.prod: ''
ms.app: cloud-app-security
ms.technology: ''
ms.assetid: 0dcc3c35-f787-4822-84c6-d4dff897dd6c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 3265f1fe6d5a75ac65ec89142c571583cb5e098a
ms.sourcegitcommit: 41fbc8e235befd240ad7a1eed52339cfafb5d906
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2018
ms.locfileid: "35251704"
---
*적용 대상: Microsoft Cloud App Security*



# <a name="generate-data-management-reports"></a>데이터 관리 보고서 생성

Microsoft Cloud App Security를 사용하면 클라우드 앱의 파일 개요를 제공하는 보고서를 생성할 수 있습니다.

보고서를 생성하려면

1. **파일**로 이동합니다. 
2. 오른쪽 위 모서리에서 점 세 개를 클릭하고 **데이터 관리 보고서**에서 다음 보고서 중 하나를 선택합니다.

   ![보고서](./media/reports.png) I
## <a name="data-sharing-overview"></a>데이터 공유 개요 

이 보고서는 클라우드 앱에 저장된 파일 수를 액세스 권한에 따라 나누어서 보여 줍니다. 액세스하기 쉽고 어디에서나 이용 가능하므로 클라우드 앱에서는 쉽게 공유할 수 있습니다. 소유자를 제외한 사용자와 공유되지 않은 파일을 개인 파일이라고 합니다. 파일이 공유된 경우 Cloud App Security는 다음 네 가지 유형의 상태를 구별합니다. <br> - 공개적으로 공유된(웹) 파일은 검색 엔진 결과를 통해서도 인증 없이 액세스할 수 있는 파일입니다.<br> - 공개적으로 공유된 파일은 링크를 사용하여 인증 없이 액세스할 수 있는 파일입니다.<br> - 외부와 공유된 파일은 조직 외부의 사용자가 클라우드 앱에 인증되면 액세스할 수 있는 파일입니다.<br> - 내부적으로 공유된 파일은 조직의 모든 또는 일부 사용자가 액세스할 수 있는 파일입니다.

## <a name="outbound-sharing-by-domain"></a>도메인별 아웃바운드 공유

이 보고서는 직원이 회사 파일을 공유한 도메인을 보여 줍니다. 각 도메인에 대해 해당 도메인과 파일을 공유하는 회사 사용자, 공유된 파일 및 공동 작업자 파일이 공유된 사람이 보고서에 자세히 표시됩니다. 각 관련 앱의 앱 페이지에 있는 [파일] 탭을 통해 이러한 도메인과의 공유를 관리하는 것이 좋습니다.

## <a name="owners-of-shared-files"></a>공유 파일의 소유자

이 보고서는 외부와 회사 파일을 공유하는 사용자를 보여 줍니다. 외부적으로 공유된 파일은 특정 외부 공동 작업자와 공유됩니다. 공개적으로 공유된 파일은 인터넷에서 누구든지 개인 링크를 통해 액세스할 수 있으며 명시적으로 링크에 노출된 사용자만 찾을 수 있습니다. 공개적으로 공유된 파일(인터넷)은 인터넷에서 누구든지 검색 엔진 결과 등을 통해 액세스할 수 있습니다. 공유하는 파일 수가 너무 많은 사용자가 있을 경우 파일 탭을 통해 이러한 과도한 공유 권한의 특성을 조사하고 해당 사용자에게 외부 공유의 사용을 자세히 파악하도록 요청하는 것이 좋습니다.


  
## <a name="see-also"></a>참고 항목 
[제어](control.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  