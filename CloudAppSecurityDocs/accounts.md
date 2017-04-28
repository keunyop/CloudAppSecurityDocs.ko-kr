---
title: "클라우드 앱 계정 보기 | Microsoft 문서"
description: "이 항목의 내용"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/23/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5d5ccc55fe0d9c3fea93446daebfcbd5bbed8c8d
ms.sourcegitcommit: fd3b6c04cec30f7c9300cc02d29d562d17bf43ea
translationtype: HT
---
# <a name="accounts"></a>계정
Cloud App Security에서는 연결된 앱의 모든 계정을 볼 수 있습니다. 앱 커넥터를 사용하여 앱에 Cloud App Security를 연결하면 Cloud App Security에서 앱과 연결된 모든 계정을 검색합니다. 계정 페이지에서 해당 계정, 구성원이 속한 그룹, 별칭 및 사용하는 앱을 조사할 수 있습니다. 


**계정** 로그를 필터링하여 특정 계정을 찾고 여러 유형의 계정을 심층 분석할 수 있습니다. 예를 들어 작년 이후 액세스하지 않은 모든 외부 계정을 필터링할 수 있습니다. 계정을 기준으로 정책을 만든 다음 경고를 받을 활동 및 조치를 정의할 수 있습니다. 

**계정** 페이지에서 다음을 비롯하여 문제에 대해 계정을 쉽게 조사할 수 있습니다.  

-   특정 서비스에서 오랫동안 활성화되지 않은 계정이 있는지 확인(해당 서비스에 대해 해당 사용자의 라이선스를 해지할 수 있음)  
-   관리자 권한이 있는 사용자의 목록을 필터링할 수 있음  

-   활성화되어 있지만 더 이상 조직에 속하지 않는 사용자의 계정을 확인할 수 있음  

-   특정 앱에 대한 사용자 권한을 해지하거나(앱에 따라 다름) 특정 사용자가 다단계 인증을 수행하도록 요구할 수 있음
    
-   각 사용자 그룹에 포함되는 계정을 확인할 수 있음  

-   각 계정에서 액세스하는 앱 및 특정 계정에 대해 삭제된 앱을 확인할 수 있음
    
-   또한 사용자의 계정을 심층 분석하고 **사용자 일시 중단** 또는 **사용자의 공동 작업 제거** 같은 관련 거버넌스 작업을 선택할 수 있습니다. 사용자를 Azure Active Directory에서 가져온 경우 **Azure AD account settings**(Azure AD 계정 설정)를 클릭하여 그룹 관리, 다단계 인증, 사용자 로그인 세부 정보, 로그인 차단 기능 등과 같은 고급 사용자 관리 기능에 쉽게 액세스할 수도 있습니다.

![계정 화면](./media/accounts-page.png)

## <a name="account-filters"></a>계정 필터
다음은 적용할 수 있는 계정 필터 목록입니다. 대부분의 필터는 매우 강력한 정책 만들기 도구를 제공하기 위해 NOT뿐만 아니라 여러 값을 지원합니다.  
  
- **계정 이름**: 계정 이름은 사용자의 기본 별칭이지만 프록시 주소, 별칭, SID 같은 다른 Microsoft 계정(Office 365 및 Azure Active Directory)의 기타 ID가 지원되며 기본 별칭 아래에 통합됩니다.

- **Affiliation**(소속): 소속은 **내부** 또는 **외부**가 됩니다. 내부에 있는 사용자 및 계정을 설정하려면 **설정**에서 내부 조직의 **IP 주소 범위**를 설정합니다. 계정에 관리자 권한이 있는 경우 [계정] 테이블의 아이콘이 빨간색 타이 ![계정 관리자 아이콘](./media/accounts-admin-icon.png)와 함께 표시됩니다.

- **앱**: 조직의 계정에서 사용하는 모든 API 연결 앱을 필터링할 수 있습니다.

- **도메인**: 특정 도메인의 사용자를 필터링할 수 있습니다.

- **Last seen**(마지막 확인): **last seen**(마지막 확인) 필터를 사용하면 유휴 상태이고 한동안 아무런 활동도 하지 않은 사용자의 계정을 찾을 수 있습니다.

- **Organization/Department**(조직/부서): 특정 Azure Active Directory 또는 Office 365 조직 그룹의 구성원을 필터링할 수 있습니다.

- **사용자 그룹**: Cloud App Security에서 사용자 그룹(기본 제공 사용자 그룹 및 가져온 사용자 그룹)의 구성원을 필터링할 수 있습니다.


## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  