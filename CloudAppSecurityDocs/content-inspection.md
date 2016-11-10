---
title: "콘텐츠 검사 | Microsoft 문서"
description: "이 문서에서는 클라우드의 데이터에 대해 DLP 콘텐츠 검사를 수행할 때 Cloud App Security에서 수행하는 프로세스에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: ea1854d6bf32e01afe6183409b68ded32ee37dd1


---

# <a name="content-inspection"></a>콘텐츠 검사
이 문서에서는 클라우드의 데이터에 대해 DLP 콘텐츠 검사를 수행할 때 Cloud App Security에서 수행하는 프로세스에 대해 설명합니다. 


Cloud App Security 콘텐츠 검사는 다음과 같이 작동합니다.
1. Cloud App Security에서 모든 드라이브의 모든 관련 파일에 대해 연속 검색을 수행합니다. 
2. Cloud App Security에서 새롭거나 변경된 것으로 감지되는 드라이브 및 이벤트에 대해 NRT(근 실시간) 검색을 수행합니다. 

연속 검색과 NRT 검색의 파일 모두 검사를 위해 큐에 추가됩니다. 검색 큐에서 파일의 순서는 드라이브의 검색 및 파일에 대한 활동에 따라 설정됩니다. 파일은 파일 메타데이터가 지원되는 MIME 형식으로 표시되는 경우에만 검색됩니다. 이 검색은 데이터 검색과 관련된 파일(문서, 이미지, 프레젠테이션, 스프레드시트, 텍스트 및 zip/보관 파일)에 대해 수행됩니다.  

파일을 검색한 후에는 다음 작업이 수행됩니다.

1. Cloud App Security에서 콘텐츠 자체가 아니라 메타데이터와 관련된 모든 사용자 지정 정책을 적용합니다. 예를 들어 파일이 20MB 이상인 경우 경고하는 정책 또는 docx 파일이 OneDrive에 저장되는 경우 경고하는 정책이 있습니다. 

2. 콘텐츠 검사가 필요한 정책이 있고 파일이 콘텐츠 검사 조건을 충족하는 경우 콘텐츠는 검사를 위해 큐에 대기됩니다. 큐 길이는 테넌트의 크기 및 검색이 필요한 파일의 수에 따라 달라집니다. 

3. 이제 **조사** > **파일**로 이동하고 파일을 클릭하여 콘텐츠 검사의 상태를 확인할 수 있습니다. 파일의 세부 정보와 함께 열리는 파일 창의 **콘텐츠 검사 상태**에 다음 중 하나가 표시됩니다. 

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

## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  


<!--HONumber=Oct16_HO4-->


