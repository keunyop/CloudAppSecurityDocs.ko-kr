---
title: "최상의 결과를 위해 Cloud App Security 포털에서 조직의 설정 제공 | Microsoft 문서"
description: "이 문서에서는 Cloud App Security에서 조직에 관한 정보를 제공하는 방법을 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: cb2b4b26ee9a5f0340409090318fcbe1421b90d5
ms.sourcegitcommit: 50fac1cec86dfb8170ba9c63a8f58a4bf24e3c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2017
---
# <a name="basic-set-up"></a>기본 설정
다음 절차에서는 Cloud App Security 포털을 사용자 지정하기 위한 지침을 제공합니다.
  
## <a name="set-up-the-portal"></a>포털 설정  
  
1.  Cloud App Security 포털 메뉴 모음에서 설정 아이콘 ![설정 아이콘](./media/settings-icon.png "설정 아이콘")을 클릭하고 **일반 설정**을 선택하여 다음을 구성합니다.  
     
     ![일반 설정](./media/general-settings.png "일반 설정")  
  
3.  **조직 정보**에서 조직에 대한 **조직 표시 이름**을 제공하는 것이 중요합니다. 이 이름은 시스템에서 전송하는 메일 및 웹 페이지에 표시됩니다.  
  
4. **환경 이름**(테넌트)을 제공합니다. 이는 여러 테넌트를 관리하는 경우에 특히 중요합니다.  
  
4. 시스템에서 전송하는 메일 알림과 웹 페이지에 표시되는 **로고**를 제공할 수도 있습니다. 로고는 최대 크기가 150 x 50 픽셀인 투명 배경의 png 파일이어야 합니다.  

4.  **관리되는 도메인**의 목록을 추가하세요. Cloud App Security에서는 관리되는 도메인을 사용하여 내부 사용자, 외부 사용자, 공유해야 하는 파일 및 공유하면 안 되는 파일을 확인하므로 이 단계는 중요합니다. 이 정보는 보고서와 경고에 사용됩니다.  
> [!NOTE] 
> - 내부로 구성되지 않은 도메인의 사용자는 외부로 표시되며 활동이나 파일이 검색되지 않습니다.

5. Azure Information Protection 통합을 사용하여 통합하는 경우 자세한 내용은 [Azure Information Protection 통합](azip-integration.md)을 참조하세요. 
  
  
6.  포털 설정을 백업하려는 경우 언제든지 이 화면에서 백업할 수 있습니다. **포털 설정 내보내기**를 클릭하여 정책 규칙, 사용자 그룹 및 IP 주소 범위를 비롯한 모든 포털 설정이 포함된 json 파일을 만듭니다.  
  
       



> [!NOTE] 
> ExpressRoute를 사용할 경우, Cloud App Security는 Azure에 배포되고 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)와 완전히 통합됩니다. 검색 로그 업로드를 포함하여 Cloud App Security에 전송된 Cloud App Security 앱 및 트래픽과의 모든 상호 작용은 대기 시간, 성능 및 보안 향상을 위해 ExpressRoute **공용 피어링**을 통해 라우팅됩니다. 고객 측에서 필요한 구성 단계는 없습니다.  
    공용 피어링에 대한 자세한 내용은 [ExpressRoute 회로 및 라우팅 도메인](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/)을 참조하세요.  
    
## <a name="see-also"></a>참고 항목  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  