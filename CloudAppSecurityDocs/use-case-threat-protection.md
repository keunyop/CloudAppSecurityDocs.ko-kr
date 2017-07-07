---
title: "위협으로부터 조직 보호 | Microsoft Docs"
description: "이 항목에서는 조직이 클라우드 환경에서 발생할 수 있는 위험 요소를 방지하기 위한 시나리오를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/27/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 7bad1e1ae6196b684ac35d063558fad22bc3689f
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2017
---
# <a name="protecting-your-organization-against-threats"></a>위협으로부터 조직 보호  

위험 수준이 높은 사용 및 클라우드 보안 문제를 식별하고 비정상적인 사용자 동작을 감지하고 연결된 클라우드 앱에서 발생할 수 있는 위협을 방지합니다. 사용자 및 관리자 활동을 파악하고 위험하다고 간주하는 특정 활동이 사용 권한 부여 환경에서 발생하는 경우 또는 의심스러운 동작에 대해 자동으로 경고하는 정책을 정의합니다. 방대한 양의 Microsoft 위협 인텔리전스 및 보안 연구 데이터를 활용합니다. 위협 검색 정책을 통해 사용 권한 앱에 필요한 보안 제어가 모두 구현되어 있는지 확인하고 지속적으로 앱을 제어할 수 있습니다.
 
## <a name="mass-download-by-a-single-user-data-exfiltration-by-an-insider"></a>단일 사용자에 의한 대용량 다운로드(참가자에 의한 데이터 반출)

이 사용 사례는 Office 365, G Suite, Box, Dropbox, Salesforce에 적용됩니다.

### <a name="the-threat"></a>위협
악의적인 참가자가 짧은 기간에 여러 파일을 다운로드하거나 액세스하여 Office 365 또는 다른 클라우드 앱에서 데이터를 반출할 수 있습니다.

### <a name="the-solution"></a>해결 방법
사용자가 짧은 기간 내에 엄청난 수의 파일을 다운로드하거나 액세스하는 경우를 감지합니다.

#### <a name="prerequisites"></a>필수 구성 요소

하나 이상의 클라우드 앱을 Cloud App Security에 [연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)합니다.

#### <a name="setting-up-monitoring"></a>모니터링 설정

1.  기본적으로 Cloud App Security는 네트워크를 검색하여 사용자가 클라우드에서 일반적으로 수행하는 작업에 대한 패턴과 이 작업을 수행하는 시기 및 사용자가 일반적으로 수행하는 작업을 파악하는 기준을 설정합니다. 

2. 클라우드 앱에서 많은 양의 다운로드가 발생하는지 감시하고 일반적인 범위를 벗어나는 동작이 발생하는 경우 경고하는 정책을 설정합니다.

    1. **정책** 페이지에서 [ **활동 정책 만들기**](user-activity-policies.md)를 클릭합니다. 
   

    2. [**정책 템플릿**](policy-template-reference.md) 필드에서 **단일 사용자의 대량 다운로드**를 선택합니다.
    
    3. 필요에 따라 반복 활동 필터를 미세 조정합니다.
    
    4. **만들기**를 클릭합니다. 
   
     
2. 일치 항목 조사
    
    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동해 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하고 파일 서랍을 열어 일치 항목을 조사할 수 있습니다. 서랍에서 이 활동이 일치하는 다른 정책을 확인할 수 있습니다. 
    
    3. **활동 서랍**에서 활동 개체를 클릭하고 나서 파일 이름을 클릭하여 사용자가 다운로드한 파일을 확인할 수 있습니다. 이렇게 하면 파일 테이블에서 해당 파일로 이동합니다. 여기에서 파일이 공유된 사용자가 해당 파일을 소유하는지 확인할 수 있고 이를 통해 이러한 파일이 사용자가 일반적으로 작업하는 파일인지 또는 다운로드하면 안 되는 내부 IP인지 확인할 수 있습니다.
     


#### <a name="validating-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 정책에서 설정한 기간(예: 5분 이내에 30개 다운로드)에 따라 단기간 내에 연결된 클라우드 앱에서 설정한 임계값보다 많은 문서를 다운로드합니다.
3. 정책 보고서로 이동합니다. 활동 정책 일치 항목이 곧 나타납니다. 
4. 일치 항목을 클릭하여 다운로드된 파일을 확인할 수 있습니다.  

#### <a name="removing-the-risk"></a>위험 제거

유효성을 검사하고 정책을 미세 조정한 후 정책과 일치했을 수 있는 가양성(예: 파일을 동기화하는 서비스 계정, 회사 이벤트의 사진 폴더 등)을 제거합니다. 그런 후 다음을 수행합니다. 
  1. [거버넌스 작업](governance-actions.md)을 수행하여 활동 서랍에서 활동을 열고 **활동 개체**에서 파일 이름을 클릭합니다.

  2. 사용자에게 연락하여 컴퓨터에 그렇게 많은 회사 파일 복사본이 필요한 이유를 확인합니다.

 
## <a name="admin-activity-from-outside-your-organizations-network"></a>조직 네트워크 외부의 관리자 활동

이 사용 사례는 Office 365, G Suite, Box, Dropbox, Salesforce 및 Okta에 적용됩니다.

### <a name="the-threat"></a>위협
관리자 계정이 외부 공격자에 의해 손상되었습니다. 관리자 계정은 가장 높은 권한을 가지고 조직의 모든 정보에 액세스할 수 있으므로 조직에서 가장 중요한 계정입니다. 일반적으로 관리 활동은 사무실에서 관리자 작업의 일부로 수행되어야 하고 원격 위치나 알 수 없는 장치에서는 수행되면 안 됩니다.

### <a name="the-solution"></a>해결 방법
관리자인 사람이 외부 IP에서 클라우드 응용 프로그램에 액세스하여 관리자 활동을 수행하는 경우를 감지합니다.

#### <a name="prerequisites"></a>필수 구성 요소

- 하나 이상의 클라우드 앱을 Cloud App Security에 [연결](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)합니다.

- **설정** > **IP 주소 범위**로 이동하고 내부 서브넷 및 외부 공용 IP의 IP 주소 범위를 둘 다 추가하고 **회사**로 태그를 지정합니다.

#### <a name="setting-up-monitoring"></a>모니터링 설정

1.  클라우드 앱에서 관리자 활동이 네트워크 외부에서 발생하는지 감시하고 일반적인 범위를 벗어나는 동작이 발생하는 경우 경고하는 정책을 설정하여 클라우드 앱 모니터링을 시작합니다.

    1. **정책** 페이지에서 [ **활동 정책 만들기**](user-activity-policies.md)를 클릭합니다. 
   

    2. [**정책 템플릿**](policy-template-reference.md) 필드에서 **회사 외 IP 주소에서 관리 활동**을 선택하고, **활동 유형**을 **로그온**으로 설정하고, **사용자**, **그룹에서**를 차례로 선택하고, 관리자가 속한 그룹을 선택합니다.
    
    3. 정책을 미세 조정하여 의심스러운 동작으로 간주할 반복 활동 수를 설정할 수 있습니다.
    
    4. **만들기**를 클릭합니다. 
   
     
2. 일치 항목 조사
    
    1. **정책** 페이지에서 정책 이름을 클릭하여 **정책 보고서**로 이동해 정책에 대해 트리거된 일치 항목을 검토합니다.

    2. 특정 일치 항목을 클릭하고 파일 서랍을 열어 일치 항목을 조사할 수 있습니다. 서랍에서 이 활동이 일치하는 다른 정책을 확인할 수 있습니다. 
     
#### <a name="validating-your-policy"></a>정책 유효성 검사

1. 경고를 시뮬레이트하려면 회사 네트워크에 속하지 않은 IP 주소를 사용하는 컴퓨터에서 관리 활동을 수행하여, 정책에서 설정한 기간(예: 5분 이내에 1개 활동)에 따라 단기간 내에 수행하는 활동 수가 설정한 임계값보다 큰지 확인합니다.
3. 정책 보고서로 이동합니다. 활동 정책 일치 항목이 곧 나타납니다. 
4. 일치 항목을 클릭하여 수행된 활동을 확인할 수 있습니다. 

#### <a name="removing-the-risk"></a>위험 제거

유효성을 검사하고 정책을 세밀하게 조정한 후 정책과 일치할 수 있는 가능한 거짓 긍정을 제거하세요. 그런 후 다음을 수행합니다. 
  1. [거버넌스 작업](governance-actions.md)을 수행하여 활동 서랍에서 활동을 열고 **사용자**의 이름을 클릭합니다.

  2. 열리는 사용자 페이지에서 지난달의 사용자 활동 그래프와 그룹 멤버 자격, 앱 활동, 계정 및 지난달에 사용자가 활성 상태였던 위치를 확인할 수 있습니다. 
  
  3. 필요한 경우 **연락처**를 클릭하여 메일 메시지를 사용자에게 보내 해당 계정이 위반되었음을 경고할 수 있습니다.

 ![자동 거버넌스 외부](./media/auto-gov-external.png)

   2. 완전하게 유효성을 검사한 후 자동 거버넌스 작업을 수행하도록 설정할 수 있습니다. 예를 들어 **사용자 일시 중단** 또는 **사용자의 공동 작업 제거**를 수행할 수 있습니다.


## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  