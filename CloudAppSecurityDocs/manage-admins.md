---
title: Cloud App Security 포털에 대한 관리자 액세스 관리
description: 이 문서에서는 Cloud App Security 포털에 대한 관리자 액세스를 설정하는 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: c347b94688b070302de12651a75344213e4bcacc
ms.sourcegitcommit: 9f322632666636de12ac332349130d7961dbbb81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2019
ms.locfileid: "54059424"
---
# <a name="manage-admin-access"></a>관리자 액세스 관리

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security는 역할 기반 액세스 제어를 지원합니다. 기본적으로 특정 [Office 365 관리자 역할](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 및 [Azure AD(Azure Active Directory) 관리자 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)은 Microsoft Cloud App Security에 액세스할 수 있습니다. 이 문서에서는 Cloud App Security 포털에 대한 관리자 액세스를 설정하는 지침을 제공합니다. 관리자 역할 할당에 대한 자세한 내용은 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) 및 [Office 365](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles)에 대한 문서를 참조하세요.

## <a name="office-365-and-azure-ad-roles-with-access-to-cloud-app-security"></a>Cloud App Security에 액세스할 수 있는 Office 365 및 Azure AD 역할

기본적으로 다음 Office 365 및 Azure AD 관리자 역할은 Microsoft Cloud App Security에 액세스할 수 있습니다.

- **글로벌 관리자 및 보안 관리자:** **모든 권한**이 있는 관지라는 Cloud App Security에서 모든 권한을 가집니다. 그들은 관리자 추가, 정책 및 설정 추가, 로그 업로드, 거버넌스 작업을 수행할 수 있습니다.

- **준수 관리자:** 읽기 전용 권한을 가지며 경고를 관리할 수 있습니다. 파일 정책을 생성 및 수정하고 파일 관리 작업을 허용하며 데이터 관리에서 모든 기본 보고서를 볼 수 있습니다. 

- **보안 독자:** 읽기 전용 권한을 가지며 경고를 관리할 수 있습니다. 보안 reader는 다음 작업을 수행할 수 없습니다.

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

- **앱/인스턴스 관리자:** 선택한 앱의 인스턴스 또는 특정 앱에서만 처리되는 Microsoft Cloud App Security의 모든 데이터에 대한 권한을 가집니다. 예를 들어 Box European 인스턴스에 대한 사용자 관리 권한을 제공합니다. 관리자는 파일, 활동, 정책 또는 경고 여부에 관계없이 Box European 인스턴스에 관련된 데이터만 다음과 같이 볼 수 있습니다.

  - 활동 페이지 - 특정 앱에 대한 활동만
  - 경고 - 특정 앱과 관련된 경고만
  - 정책 - 모든 정책을 볼 수 있으며, 앱/인스턴스에서만 처리되는 정책만 편집하거나 만들 수 있음
  - 계정 - 특정 앱/인스턴스에 대한 계정만
  - 앱 사용 권한 - 특정 앱/인스턴스에 대한 사용 권한만
  - 파일 페이지 - 특정 앱/인스턴스의 파일만
  - 조건부 액세스 앱 제어 - 사용 권한 없음
  - Cloud Discovery 활동 - 사용 권한 없음
  - 보안 확장 - 사용자 권한이 있는 API 토큰에 대한 사용 권한만
  - 거버넌스 작업 - 특정 앱/인스턴스에 대해서만 

- **그룹 관리자:** 여기에서 선택한 특정 그룹에서만 처리되는 Microsoft Cloud App Security의 모든 데이터에 대한 권한을 가집니다. 예를 들어, 사용자에게 “독일 - 모든 사용자” 그룹에 대한 관리자 권한을 부여하면 관리자는 다음과 같이 해당 사용자 그룹에 대해서만 Microsoft Cloud App Security에서 정보를 보고 수정할 수 있습니다.

  - 활동 페이지 - 그룹의 사용자에 대한 활동만
  - 경고 - 그룹의 사용자와 관련된 경고만
  - 정책 - 모든 정책을 볼 수 있으며, 그룹의 사용자에서만 처리되는 정책만 편집하거나 만들 수 있음
  - 계정 - 그룹의 특정 사용자에 대한 계정만
  - 앱 권한 - 사용 권한 없음
  - 파일 페이지 - 사용 권한 없음
  - 조건부 액세스 앱 제어 - 사용 권한 없음
  - Cloud Discovery 활동 - 사용 권한 없음
  - 보안 확장 - 그룹의 사용자가 있는 API 토큰에 대한 사용 권한만
  - 거버넌스 작업 - 그룹의 특정 사용자에 대해서만


## <a name="override-admin-permissions"></a>관리자 사용 권한 재정의

Azure Active Directory 또는 Office 365의 관리자 권한을 재정의하려면 Cloud App Security에 사용자를 수동으로 추가하고 사용자에게 권한을 할당하면 됩니다.
예를 들어 Azure Active Directory의 보안 reader인 Stephanie에게 Cloud App Security의 **모든 권한**을 할당하려면 Cloud App Security에 Stephanie를 수동으로 추가하고 **모든 권한**을 할당하여 역할을 재정의하고 Cloud App Security에서 필요한 권한을 허용합니다. 

## <a name="add-additional-admins"></a>다른 관리자 추가

Azure Active Directory 관리자 역할에 사용자를 추가하지 않고 Cloud App Security에 추가 관리자를 추가할 수 있습니다. 추가 관리자를 추가하려면 다음 단계를 수행합니다.

   >[!IMPORTANT]
   > 전역 관리자 또는 보안 관리자만 Cloud App Security에 대한 액세스 권한을 다른 사용자에게 부여할 수 있습니다.


1. 설정 코그 ![설정 아이콘](./media/settings-icon.png "설정 아이콘"), **관리자 액세스 관리**를 차례로 클릭합니다. 

2. 더하기를 클릭하여 Cloud App Security에 액세스할 수 있는 관리자를 추가합니다. 내부 또는 외부 이메일 주소를 입력하여 조직 내 또는 외부 MSSP(관리되는 보안 서비스 공급자)의 관리자가 보안 경고를 관리할 수 있습니다.
  
   ![관리자 추가](./media/add-admin.png)

3. 다음으로, 드롭다운을 클릭하여 관리자의 역할 유형(**전역 관리자**, **보안 읽기 권한자**, **준수 관리자**, 또는 **앱/인스턴스 관리자**)을 설정합니다. **앱/인스턴스 관리자**를 선택하는 경우 관리자가 사용 권한을 가지는 앱 및 인스턴스를 선택합니다.

     >[!NOTE]
      >제한된 페이지에 액세스하거나 제한된 작업을 수행하려고 하는 액세스 권한이 제한된 관리자는 페이지에 액세스하거나 작업을 수행할 권한이 없다는 오류가 표시됩니다.

4. **관리자 추가**를 클릭합니다.  

## <a name="invite-external-admins"></a>외부 관리자 초대

Microsoft Cloud App Security를 사용하면 Microsoft Cloud App Security 포털의 관리자 권한을 가진 외부 MSSP(관리되는 보안 서비스 공급자)를 초대할 수 있습니다. 외부 사용자는 이제 관리자로 구성되고 Microsoft Cloud App Security에서 지원되는 역할 중 하나를 할당받을 수 있습니다. 또한 여러 고객 테넌트에 서비스를 제공하는 데 MSSP를 사용하기 위해 둘 이상의 테넌트에 대한 액세스 권한이 있는 관리자는 포털 내에서 테넌트를 쉽게 전환할 수 있습니다. 

테넌트 간에 전환하려면 여러 테넌트에 대한 사용 권한을 설정한 후에 사용자 아이콘을 클릭합니다. 사용 권한이 있는 테넌트의 목록이 표시됩니다. 관리할 테넌트를 선택합니다.

![테넌트 선택](./media/choose-tenant.png "테넌트 선택")

## <a name="next-steps"></a>다음 단계  
[Cloud Discovery 설정](set-up-cloud-discovery.md)   
  
  
  
