---
title: "제어 | Microsoft 문서"
description: "이 문서에서는 Cloud App Security에서 조직의 클라우드 앱 사용을 제어하기 위해 수행할 수 있는 거버넌스 작업에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bc11bbfe-ec6c-458c-8302-8112c383199d
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 9dc74c35f32c9a3dff251d6e0ac6b35a3591f4b9


---

# <a name="control"></a>컨트롤
클라우드 환경 전체의 사용자 파일에 거버넌스 작업을 적용할 수 있습니다. 클라우드를 철저하게 조사하고 알아본 후 거버넌스 작업을 사용하여 조직을 보호할 수 있습니다.  
  
## <a name="applying-governance-actions"></a>거버넌스 작업 적용  
정책 내, 내부 경고 및 **파일** 로그에서 거버넌스 작업을 적용할 수 있습니다.  
  
언제든지 **설정** 코그 ![설정 아이콘](./media/settings-icon.png "settings icon")로 이동하고 **거버넌스 로그**를 클릭하여 이전에 적용된 모든 거버넌스 작업의 상태를 검토하고 확인할 수 있습니다.  
  
실패한 거버넌스 작업의 경우 다시 시도 아이콘 ![다시 시도 아이콘](./media/retry-icon.png "retry icon") 을 클릭하여 다시 적용합니다.  
  
정책, 위반 및 앱 유형에 따라 다양한 거버넌스 작업을 사용할 수 있습니다.  
  
## <a name="moving-from-detection-to-automatic-remediation"></a>검색에서 자동 수정으로 이동  
정책 필터를 정의하고 사용자 지정한 후 정책 위반 시마다 수행할 자동화된 거버넌스 작업을 선택할 수 있습니다.  
수정 작업은 클라우드 공급자 API를 활용하므로 앱마다 작업이 달라질 수 있습니다.  
  
> [!NOTE]  
>  거버넌스 작업을 설정할 때는 특히 주의하세요. 파일에 대한 액세스 권한이 손실될 수 있으며 복구할 수 없습니다.  
> 여러 검색 필드를 사용하여 작업하려는 파일을 정확하게 나타내도록 필터 범위를 좁히는 것이 좋습니다. 필터는 좁을수록 더 좋습니다.  
>   
>  지침을 보려면 필터 섹션에서 **결과 편집 및 미리 보기** 단추를 사용할 수 있습니다.  
  
![파일 정책 편집 및 결과 미리 보기](./media/file-policy-edit-and-preview-results.png "file policy edit and preview results")  
  
## <a name="migration"></a>마이그레이션  
Cloud App Security는 조직에서 누가 어떤 앱을 사용 중인지를 알려주고 새로운 앱 채택을 모니터링할 도구를 제공하여 마이그레이션을 롤아웃할 수 있도록 도와줍니다. 또한 모든 사용자가 이미 사용 중인 앱을 확인할 수 있는 도구를 제공하여 조직에서 제공해야 하는 앱 유형을 파악할 수 있게 합니다.  
  
### <a name="how-to-migrate-your-users-to-a-new-app"></a>사용자를 새 앱으로 마이그레이션하는 방법  
최근에 Office 365를 구입했으며 조직의 모든 사용자가 다른 모든 클라우드 저장소 앱의 사용을 중지하고 OneDrive 사용을 시작하도록 하는 시나리오를 가정해 보겠습니다. 수행할 수 있는 작업은 다음과 같습니다.  
  
-   **클라우드 검색 대시보드**로 이동한 다음 **범주**에서 **클라우드 저장소**를 기준으로 앱을 필터링합니다. 그런 다음 **사용자** 또는 **IP 주소**를 기준으로 결과를 정렬하고 가장 많이 사용하는 앱을 확인합니다.  
  
-   다른 앱을 사용하는 사용자를 확인할 수 있습니다.  
  
     또한 다음과 같이 이러한 앱을 드릴다운하고 해당 앱의 사용자에게 OneDrive로 마이그레이션하도록 알릴 수 있습니다.  
  
    1.  **클라우드 검색 대시보드**에서 Dropbox를 클릭한 다음 **IP 주소** 또는 **사용자** 탭을 클릭합니다.  
  
    2.  화살표 ![화살표 아이콘](./media/arrow-icon.png "arrow icon")를 클릭하고 **내보내기**를 선택합니다.  
  
### <a name="find-more-secure-alternatives"></a>더 안전한 대안 찾기  
Cloud App Security 서비스 카탈로그를 통해 사용자가 사용 중일 수 있는 위험한 앱 대신 조직에 적합한 대안을 찾을 수 있습니다.  
  
생산성 도구의 구입을 고려 중이며 사용자의 사용 여부가 확실하지 않은 시나리오를 가정해 보겠습니다.  
  
-   **클라우드 검색 대시보드**로 이동합니다.  
  
-   **범주**에서 **생산성**을 기준으로 앱을 필터링합니다.  
  
-   사용 중인 각 앱에 대해 **점수**를 검사하여 안전한지 확인하고, 안전하지 않을 경우 이유를 확인합니다.  
  
-   전체 조직에 대한 엔터프라이즈 라이선스를 구입하려는 경우 결정하기 전에 **사용자** 열을 검사하여 사용자가 이미 많이 사용하는 앱, 신뢰할 수 있는지 여부 및 보유한 보안 기능을 확인하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


