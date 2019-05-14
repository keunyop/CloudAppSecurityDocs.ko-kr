---
title: Cloud App Security에서 조직의 설정 지정
description: 이 문서에서는 Cloud App Security에서 조직에 관한 정보를 제공하는 방법을 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 2889bbf3c837e0d8e086d7e7a579f2839c42b5f3
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65567836"
---
# <a name="basic-setup-for-cloud-app-security"></a>Cloud App Security에 대한 기본 설정

*적용 대상: Microsoft Cloud App Security*

다음 절차에서는 Microsoft Cloud App Security 포털을 사용자 지정하기 위한 지침을 제공합니다.

## <a name="prerequisites"></a>필수 구성 요소 
포털 액세스의 경우 Cloud App Security 포털에 액세스할 수 있도록 다음 IP 주소를 방화벽 허용 목록에 추가해야 합니다.  
  
- 104.42.231.28  
  
> [!NOTE]  
>  URL 및 IP 주소가 변경된 경우 업데이트를 가져오려면 다음에 설명된 대로 RSS를 구독합니다. [Office 365 URL 및 IP 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)  
  
## <a name="set-up-the-portal"></a>포털 설정  
  
1. Cloud App Security 포털 메뉴 모음에서 설정 코그 ![설정 아이콘](./media/settings-icon.png "설정 아이콘")을 클릭하고 **설정**을 선택하여 조직 세부 정보를 구성합니다.     

2. **조직 정보**에서 조직에 대한 **조직 표시 이름**을 제공하는 것이 중요합니다. 이 이름은 시스템에서 전송하는 이메일 및 웹 페이지에 표시됩니다.  
  
3. **환경 이름**(테넌트)을 제공합니다. 이 정보는 둘 이상의 테넌트를 관리하는 경우에 특히 중요합니다.  
  
4. 시스템에서 보내는 이메일 알림과 웹 페이지에 표시되는 **로고**를 제공할 수도 있습니다. 로고는 최대 크기가 150 x 50 픽셀인 투명 배경의 png 파일이어야 합니다.  

5. **관리되는 도메인**의 목록을 추가하세요. 관리되는 도메인을 추가하는 것은 중요한 단계입니다. Cloud App Security는 관리되는 도메인을 사용하여 내부 사용자, 외부 사용자 및 파일을 공유해야 하는지 여부를 결정합니다. 이 정보는 보고서 및 경고에 사용됩니다.  
   
    - 내부로 구성되지 않은 도메인의 사용자는 외부로 표시됩니다. 외부 사용자는 활동이나 파일을 검색하지 않습니다.

6. Azure Information Protection 통합을 사용하여 통합하는 경우 자세한 내용은 [Azure Information Protection 통합](azip-integration.md)을 참조하세요. 

    - Azure Information Protection 통합 작업을 하려면 [Office 365용 앱 커넥터](connect-office-365-to-microsoft-cloud-app-security.md)를 사용하도록 설정해야 합니다.
  
7. 포털 설정을 백업하려는 경우 언제든지 이 화면에서 백업할 수 있습니다. **포털 설정 내보내기**를 클릭하여 정책 규칙, 사용자 그룹 및 IP 주소 범위를 비롯한 모든 포털 설정이 포함된 json 파일을 만듭니다.  
  
   
> [!NOTE] 
> ExpressRoute를 사용할 경우, Cloud App Security는 Azure에 배포되고 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)와 완전히 통합됩니다. 검색 로그 업로드를 포함하여 Cloud App Security에 전송된 Cloud App Security 앱 및 트래픽과의 모든 상호 작용은 대기 시간, 성능 및 보안 향상을 위해 ExpressRoute **공용 피어링**을 통해 라우팅됩니다. 고객 측에서 필요한 구성 단계는 없습니다. <br></br>공용 피어링에 대한 자세한 내용은 [Express 경로 회로 및 라우팅 도메인](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/)을 참조하세요.  
    
## <a name="next-steps"></a>다음 단계  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
