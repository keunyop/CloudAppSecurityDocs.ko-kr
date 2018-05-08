---
title: Cloud App Security 포털에 대한 관리자 액세스 관리 | Microsoft 문서
description: 이 항목에서는 Cloud App Security 포털에 대한 관리자 액세스를 설정하는 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/29/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 82df91691ec5543075a9b3c11dfef1e11eb4fae9
ms.sourcegitcommit: c5dbeb75e409518feaa26200e9a02c59accc8dcc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
*적용 대상: Microsoft Cloud App Security*


## <a name="managing-admin-access"></a>관리자 액세스 관리

Microsoft Cloud App Security는 역할 기반 액세스 제어를 지원합니다. 기본적으로 다음 Office 365 및 Azure AD 관리자 역할은 Microsoft Cloud App Security에 액세스할 수 있습니다.

- 전역 관리자 및 보안 관리자: **모든 권한**을 가진 관리자는 Cloud App Security에서 관리자를 추가하고, 정책 및 설정을 추가하고, 로그를 업로드하고, 거버넌스 작업을 수행할 모든 권한을 가집니다.

- 준수 관리자: 읽기 전용 권한을 가지며 경고를 관리할 수 있습니다. 파일 정책을 생성 및 수정하고 파일 관리 작업을 허용하며 데이터 관리에서 모든 기본 보고서를 볼 수 있습니다. 

- 보안 독자: 읽기 전용 권한을 가지며 경고를 관리할 수 있습니다. 보안 독자는 다음을 수행할 수 없습니다.
      - 정책 만들기 또는 기존 정책 편집/변경 
      - 거버넌스 작업 수행 
      - 검색 로그 업로드
      - 타사 앱 금지 및 승인
      - IP 주소 범위 설정 페이지 액세스 및 보기
      - 모든 설정 페이지 액세스 및 보기 
      - 검색 설정 액세스 및 보기 
      - 앱 커넥터 페이지 액세스 및 보기
      - 거버넌스 로그 액세스 및 보기 
      - 스냅숏 보고서 관리 페이지 액세스 및 보기 

- 앱/인스턴스 관리자: 여기에서 선택한 앱의 인스턴스 또는 특정 앱에서만 처리되는 Microsoft Cloud App Security의 모든 데이터에 대한 권한을 가집니다. 예를 들어 사용자에게 Box European 인스턴스에 대한 관리자 권한을 제공하는 경우, 관리자는 파일이든, 활동이든, 정책이든, 경고든 상관없이 다음과 같이 이 앱 인스턴스와 관련된 데이터만 볼 수 있습니다.
      - 활동 페이지 - 태그가 지정된 엔터티에 대한 활동만
      - 경고 - 특정 앱과 관련된 경고만
      - 정책 - 모든 정책을 볼 수 있으며, 앱/인스턴스에서만 처리되는 정책만 편집하거나 만들 수 있음
      - 계정 - 특정 앱/인스턴스에 대한 계정만
      - 앱 사용 권한 - 특정 앱/인스턴스에 대한 사용 권한만
      - 파일 페이지 - 특정 앱/인스턴스의 파일만
      - 조건부 액세스 앱 제어 - 사용 권한 없음
      - Cloud Discovery 활동 - 사용 권한 없음
      - 보안 확장 - 사용자 권한이 있는 API 토큰에 대한 사용 권한만
      - 거버넌스 작업 - 특정 앱/인스턴스에 대해서만 

자세한 내용은 [Azure Active Directory에서 관리자 역할 할당](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles)을 참조하세요.

다음 단계를 수행하여 Azure Active Directory 관리자 역할에 사용자를 추가하지 않고 Cloud App Security에 추가 관리자를 추가할 수도 있습니다.

1. 설정 코그 ![설정 아이콘](./media/settings-icon.png "설정 아이콘"), **관리자 관리**를 차례로 클릭합니다. 

2. 더하기를 클릭하여 Cloud App Security에 액세스할 수 있는 관리자를 추가합니다.
  
  ![관리자 추가](./media/add-admin.png)
    
3. 다음으로, 드롭다운을 클릭하여 관리자의 역할 유형(**전역 관리자**, **보안 읽기 권한자**, **준수 관리자**, 또는 **App/Instance admin**(앱/인스턴스 관리자))을 설정합니다. **App/Instance admin**(앱/인스턴스 관리자)을 선택하는 경우 관리자가 사용 권한을 가지는 앱 및 인스턴스를 선택합니다.

     >[!NOTE]
      >제한된 페이지에 액세스하거나 제한된 작업을 수행하려고 하는 액세스 권한이 제한된 관리자는 페이지에 액세스하거나 작업을 수행할 권한이 없다는 오류가 표시됩니다.
4. **관리자 추가**를 클릭합니다.  

   >[!NOTE]
    >전역 관리자 또는 보안 관리자만 Cloud App Security에 대한 액세스 권한을 다른 사용자에게 부여할 수 있습니다.
  
**관리자 권한을 재정의하려면:**

Azure Active Directory 또는 Office 365의 관리자 권한을 재정의하려면 Cloud App Security에 사용자를 수동으로 추가하고 사용자에게 권한을 할당하면 됩니다.
예를 들어 Azure Active Directory의 보안 독자인 Stephanie에게 Cloud App Security의 **모든 권한**을 할당하려면 Cloud App Security에 Stephanie를 수동으로 추가하고 **모든 권한**을 할당하여 역할을 재정의하고 Cloud App Security에서 원하는 권한을 허용합니다. 


Cloud App Security에 다른 관리자를 추가하려면:
1. 설정 코그 ![설정 아이콘](./media/settings-icon.png "설정 아이콘"), **관리자 액세스 관리**를 차례로 클릭합니다. 

2. Cloud App Security에 액세스할 수 있어야 하는 관리자를 추가합니다. 액세스 수준을 선택하고 **닫기**를 클릭합니다.

## <a name="see-also"></a>참고 항목  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  