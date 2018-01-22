---
title: "Cloud App Security에서 콘텐츠 검사 오류 문제 해결 | Microsoft 문서"
description: "이 항목에서는 콘텐츠 검사 상태 목록과 해당 상태의 의미에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 359eb77f-e719-4c50-9b62-6ef64149a5a5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: be49af4df563d4aa2a05dd4830d2dd8835fa90d3
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2018
---
# <a name="troubleshooting-content-inspection"></a>콘텐츠 검사 문제 해결
|콘텐츠 검사 상태|설명|
|----|----|
|완료|콘텐츠 검사가 완료되었습니다.|
|해당 없음|이 파일에는 콘텐츠 검사가 적용되지 않습니다. 정책에 이 파일의 콘텐츠 검사가 필요하지 않거나 파일 형식이 지원되지 않기 때문일 수 있습니다.|
|Pending|파일이 현재 콘텐츠 검사 큐에 있습니다.|
|실패: 다운로드 오류|Cloud App Security에서 검사할 파일을 다운로드하지 못했습니다.|
|실패: 파일이 암호화됨|파일의 암호를 해독할 수 없습니다.|
|실패: 파일이 손상됨|파일이 어떤 방식으로든 손상되어 검사할 수 없습니다.|
|실패: 내부 오류|파일을 검사하려고 할 때 알 수 없는 오류가 발생했습니다.|
|실패: 외부 DLP 오류|외부 DLP에서 오류가 발생하여 Cloud App Security에서 콘텐츠를 검사하지 못했습니다.|
|실패: 파일 크기 초과|파일 제한은 파일 크기 및 문자 수에 따라 달라집니다.|
|실패: 파일 액세스 거부됨|파일이 클라우드 외부에 있으며 Cloud App Security에서 액세스할 수 없습니다.|
|실패: 파일이 삭제됨|파일을 더 이상 클라우드에 없으며 검사할 수 없습니다.|
|실패: 지원되지 않는 파일 형식|이 파일 형식에서는 Cloud App Security가 콘텐츠 검사를 수행할 수 없습니다. 파일 형식이 지원되지 않거나 파일이 실제로 예상 파일 형식이 아니기 때문일 수 있습니다.|

> [!NOTE]
> 검색 상태에 대시가 표시되는 경우 검색할 파일이 큐에 대기 되지 않은 것입니다. 콘텐츠 검사 정책을 설정하는 방법에 대한 자세한 내용은 [파일 정책](data-protection-policies.md)을 참조하세요.

## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  