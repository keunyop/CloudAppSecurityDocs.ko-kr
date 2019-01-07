---
title: 검색된 앱 차단 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 검색된 앱에 대한 차단 스크립트를 내보내기 위한 절차를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 00c5063d93f469d91512e6bb37338855093e6bdf
ms.sourcegitcommit: b86c3afd1093fbc825fec5ba4103e3a95f65758e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53175570"
---
# <a name="govern-discovered-apps"></a>검색된 앱 제어

*적용 대상: Microsoft Cloud App Security*

환경에서 검색된 앱 목록을 검토한 후 다음 방법으로 원하지 않는 앱 사용으로부터 환경을 보호할 수 있습니다.


## <a name="BKMK_SanctionApp"></a> 앱 사용 권한 부여/취소 

행 끝에 있는 점 세 개를 클릭하여 위험한 특정 앱의 사용 권한을 취소할 수 있습니다. 그런 다음, **사용 권한 취소**를 선택합니다. 앱의 사용 권한을 취소해도 사용이 차단되지는 않지만 Cloud Discovery 필터를 통해 사용을 더 쉽게 모니터링할 수 있습니다. 그런 다음, 사용자에게 사용 권한이 취소된 앱에 대해 알리고 사용하기에 안전한 대체 앱을 제안할 수 있습니다.

![비사용 권한으로 태그 지정](./media/tag-as-unsanctioned.png)  

사용 권한을 부여 또는 취소할 앱 목록이 있는 경우 확인란을 사용하여 관리할 앱을 선택한 다음, 작업을 선택합니다.

비사용 권한 앱 목록을 조회하려면 [Cloud App Security API를 사용하여 차단 스크립트를 생성](https://us.portal.cloudappsecurity.com/api-docs/#generate-block-script)할 수 있습니다.

> [!NOTE]
> 테넌트에서 Zscaler NSS를 사용하는 경우 비사용 권한으로 표시한 모든 앱은 자동으로 Cloud App Security에 의해 차단되며, 차단 스크립트 만들기에 관한 다음 섹션은 불필요합니다. 자세한 내용은 [Zscaler와 통합](zscaler-integration.md)을 참조하세요.

## <a name="export-a-block-script-to-govern-discovered-apps"></a>검색된 앱을 관리하기 위해 차단 스크립트 내보내기

Cloud App Security를 통해 기존 온-프레미스 보안 어플라이언스를 사용하여 비사용 권한 앱에 대한 액세스를 차단할 수 있습니다. 전용 차단 스크립트를 생성하고 어플라이언스로 가져올 수 있습니다. 이 솔루션에는 프록시에 대한 조직의 모든 웹 트래픽을 리디렉션할 필요가 없습니다.

1. Cloud Discovery 대시보드에서 차단할 모든 앱을 **Unsanctioned**(비사용 권한)으로 태그 지정합니다.

   ![비사용 권한으로 태그 지정](./media/tag-as-unsanctioned.png)  

2. 제목 표시줄에서 세 점을 클릭하고 **Generate block script...**(차단 스크립트 생성...)을 선택합니다. 

   ![차단 스크립트 생성](./media/generate-block-script.png)  

3. **Generate block script**(차단 스크립트 생성)에서 차단 스크립트를 생성할 어플라이언스를 선택합니다. 

   ![차단 스크립트 팝업 생성](./media/generate-block-script-popup.png)  

4. 그런 다음, 스크립트 생성 단추를 클릭하여 모든 비사용 권한 앱에 대한 블록 스크립트를 만듭니다. 기본적으로 파일에는 파일을 내보낸 날짜와 선택한 어플라이언스 형식으로 이름이 지정됩니다. *2017-02-19_CAS_Fortigate_block_script.txt*는 예제 파일 이름입니다. 

   ![차단 스크립트 생성 단추](./media/generate-block-script-button.png)  

5. 어플라이언스에서 생성된 파일을 가져옵니다.



## <a name="next-steps"></a>다음 단계  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  