---
title: 클라우드 앱 계정 보기 | Microsoft 문서
description: 이 항목의 내용
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/2/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 99af9274716bd11033b9a7dff947a99dc6c42f9d
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143059"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="accounts"></a>계정
Microsoft Cloud App Security에서는 연결된 앱의 계정을 파악할 수 있습니다. 앱 커넥터를 사용하여 앱에 Cloud App Security를 연결하면 Cloud App Security는 연결된 앱과 관련된 계정 정보를 읽습니다. [계정] 페이지에서 해당 계정, 사용 권한, 계정이 속한 그룹, 계정 별칭 및 사용하는 앱을 조사할 수 있습니다. 또한 Cloud App Security가 활동이나 파일 공유 등의 연결된 앱 중 하나에서 이전에 보이지 않던 새 계정을 검색하는 경우 이 계정이 해당 앱의 계정 목록에 추가됩니다. 따라서 클라우드 앱을 조작하는 외부 사용자의 활동을 파악할 수 있습니다.

관리자는 특정 사용자의 메타데이터 또는 사용자의 활동을 검색할 수 있습니다. **사용자 및 계정** 페이지는 연결된 클라우드 응용 프로그램에서 풀된 엔터티에 대한 포괄적인 세부 정보를 제공합니다. 사용자의 활동 기록 및 사용자와 관련된 보안 경고도 제공합니다.

[!INCLUDE [Handle personal data](../includes/gdpr-intro-sentence.md)]


**계정** 페이지를 필터링하여 특정 계정을 찾고 여러 유형의 계정을 심층 분석할 수 있습니다. 예를 들어 작년 이후 액세스하지 않은 모든 외부 계정을 필터링할 수 있습니다. 

**계정** 페이지에서 다음 문제를 비롯하여 계정을 쉽게 조사할 수 있습니다.  

-   특정 서비스에서 오랫동안 활성화되지 않은 계정이 있는지 확인(해당 서비스에 대해 해당 사용자의 라이선스를 해지할 수 있음)  
-   관리자 권한이 있는 사용자의 목록을 필터링할 수 있음  

-   더 이상 조직에 속하지 않지만 여전히 활성 계정을 갖고 있을 수 있는 사용자를 검색할 수 있음  

-   앱 일시 중단 또는 계정 설정 페이지로 이동과 같은 계정에 대한 거버넌스 작업을 수행할 수 있음. 거버넌스 작업의 전체 목록은 [거버넌스 로그](governance-actions.md)를 참조하세요.
    
-   각 사용자 그룹에 포함되는 계정을 확인할 수 있음  

-   각 계정에서 액세스하는 앱 및 특정 계정에 대해 삭제된 앱을 확인할 수 있음
    

![계정 화면](./media/accounts-page.png)

## <a name="account-filters"></a>계정 필터
다음은 적용할 수 있는 계정 필터 목록입니다. 대부분의 필터는 강력한 정책 만들기 도구를 제공하기 위해 NOT뿐만 아니라 여러 값을 지원합니다.  
  
- **계정 이름**: 계정 이름은 사용자의 기본 별칭이지만 프록시 주소, 별칭, SID 같은 다른 Microsoft 계정(Office 365 및 Azure Active Directory)의 기타 ID가 지원되며 기본 별칭 아래에 통합됩니다.

- **Affiliation**(소속): 소속은 **내부** 또는 **외부**가 됩니다. 내부에 있는 사용자 및 계정을 설정하려면 **설정**에서 내부 조직의 **IP 주소 범위**를 설정합니다. 계정에 관리자 권한이 있는 경우 [계정] 테이블의 아이콘이 빨간색 타이 ![계정 관리자 아이콘](./media/accounts-admin-icon.png)과 함께 표시됩니다.

- **앱**: 조직의 계정에서 사용하는 모든 API 연결 앱을 필터링할 수 있습니다.

- **도메인**: 특정 도메인의 사용자를 필터링할 수 있습니다.

- **Last seen**(마지막 확인): **last seen**(마지막 확인) 필터를 사용하면 유휴 상태이고 한동안 아무런 활동도 하지 않은 사용자의 계정을 찾을 수 있습니다.

- **Organization/Department**(조직/부서): 연결된 앱에서 정의한 특정 조직 그룹의 구성원을 필터링할 수 있습니다.

- **사용자 그룹**: Cloud App Security에서 사용자 그룹(기본 제공 사용자 그룹 및 가져온 사용자 그룹)의 구성원을 필터링할 수 있습니다.


## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  