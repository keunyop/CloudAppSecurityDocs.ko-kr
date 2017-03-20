---
title: "검색된 앱 차단 | Microsoft 문서"
description: "이 항목에서는 검색된 앱에 대한 차단 스크립트를 내보내기 위한 절차를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/21/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ca4a10f64429c481f49c75740f651302b1c7d1ef
ms.sourcegitcommit: 7493d88e4fe7c827f870b81e2090ffcc77f1408a
translationtype: HT
---
# <a name="governing-discovered-apps"></a>검색된 앱 제어
Cloud App Security를 통해 기존 온-프레미스 보안 어플라이언스를 활용하여 비사용 권한 앱에 대한 액세스를 차단할 수 있습니다. 전용 차단 스크립트를 생성하고 여 어플라이언스로 가져옵니다.
이 솔루션에는 프록시에 대한 조직의 모든 웹 트래픽을 리디렉션할 필요가 없습니다.


## <a name="export-a-block-script-to-govern-discovered-apps"></a>검색된 앱을 관리하기 위해 차단 스크립트 내보내기

1. Cloud Discovery 대시보드에서 차단할 모든 앱을 **Unsanctioned**(비사용 권한)으로 태그 지정합니다.

   ![비사용 권한으로 태그 지정](./media/tag-as-unsanctioned.png)  

2. 제목 표시줄에서 세 점을 클릭하고 **Generate block script...**(차단 스크립트 생성...)을 선택합니다. 

   ![차단 스크립트 생성](./media/generate-block-script.png)  

3. **Generate block script**(차단 스크립트 생성)에서 차단 스크립트를 생성할 어플라이언스를 선택합니다. 

   ![차단 스크립트 팝업 생성](./media/generate-block-script-popup.png)  

4. 그런 다음 스크립트 생성 단추를 클릭합니다. 그러면 비사용 권한 앱 모두에 대한 차단 스크립트가 생성됩니다. 기본적으로 파일에는 파일을 내보낸 날짜와 선택한 어플라이언스를 사용한 이름이 지정됩니다(예: *2017-02-19_CAS_Fortigate_block_script.txt*). 

   ![차단 스크립트 생성 단추](./media/generate-block-script-button.png)  

5. 어플라이언스에서 생성된 파일을 가져옵니다.



## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  