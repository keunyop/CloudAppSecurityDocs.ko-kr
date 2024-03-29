---
title: Cloud App Security 활동 필터 및 쿼리 사용
description: 이 문서에서는 Cloud App Security 활동 필터 및 쿼리 목록을 제공하고 이를 사용하는 방법을 설명합니다.
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
ms.assetid: 9ba5c7d3-c733-4048-9b99-bf41a0f46695
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 098855853ea933e5319198978cb771c220ec22be
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65565919"
---
# <a name="activity-filters-and-queries"></a>활동 필터 및 쿼리

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 Cloud App Security 활동 필터 및 쿼리에 대한 설명과 지침을 제공합니다.

## <a name="activity-filters"></a>활동 필터

다음은 적용할 수 있는 활동 필터 목록입니다. 대부분의 필터는 강력한 정책 만들기 도구를 제공하기 위해 NOT뿐만 아니라 여러 값을 지원합니다.  
  
- 활동 ID - 해당 ID로 특정 활동만 검색합니다. 이 필터는 SIEM 에이전트 사용하여 Microsoft Cloud App Security를 SIEM에 연결할 때 유용하며, Cloud App Security 포털 내에서 경고를 자세히 조사할 수 있습니다.  
  
- 활동 개체 - 활동이 수행된 대상 개체를 검색합니다. 이 필터는 파일, 폴더, 사용자 또는 앱 개체에 적용됩니다. 
  - 활동 개체 ID - 개체의 ID(파일, 폴더, 사용자 또는 앱 ID)입니다.
  <!-- - File, folder or site URL - Enables you to select files, folders and URLs that start with a specific string.-->
  <!-- - Target object (file/folder) - Enables you to select a specific file or folder. -->
  - 항목 - 활동 개체의 이름 또는 ID를 기준으로 검색할 수 있습니다(예: 사용자 이름, 파일, 매개 변수, 사이트). **Activity object Item**(활동 개체 항목) 필터에서 특정 항목을 **포함**하거나, 특정 항목과 **같거나**, 특정 항목으로 **시작**하는 항목을 필터링할지 여부를 선택할 수 있습니다.
    
- 활동 유형 - 응용 프로그램 활동을 검색합니다.

- 관리 활동 – 관리 활동만 검색합니다.  
  
- 경고 ID - 경고 ID를 기준으로 검색합니다.

- 앱 - 특정 앱 내의 활동만 검색합니다.  
  
- 적용된 작업 - 적용된 거버넌스 작업으로 검색: 차단됨, 프록시 우회, 암호 해독됨, 암호화됨, 암호화 실패, 작업 없음

- 날짜 - 활동이 발생한 날짜입니다. 필터는 이전/이후 날짜와 날짜 범위를 지원합니다.  
  
<!--- Description – Specific keyword in the activity description, for example, all activities that include the string **user** in their description.  -->
  
- 디바이스 태그 - 규정 준수, 관리 또는 확인된 디바이스를 기준으로 검색합니다.

- 디바이스 유형 - 특정 디바이스 유형을 사용하여 수행된 활동만 검색합니다. 예를 들어, 모바일 디바이스, PC 또는 태블릿의 모든 활동을 검색합니다.  

- 파일 및 폴더 - 활동을 수행한 파일 및 폴더를 검색합니다.
    - 파일 ID - 활동을 수행한 파일 ID로 검색할 수 있습니다. 
    - 이름 - 파일 또는 폴더의 이름을 필터링합니다. 이름에서 검색 값이 **끝 문자**, **같음** 또는 **시작 문자**인지 여부를 선택할 수 있습니다.
    - 특정 파일 또는 폴더 - 특정 파일 또는 폴더를 포함하거나 제외할 수 있습니다. 파일 또는 폴더를 선택할 때 **앱**, **소유자** 또는 부분 **파일 이름**으로 목록을 필터링할 수 있습니다. 
  
- IP 주소 - 활동을 수행한 원시 IP 주소, 범주 또는 태그입니다.  
  - 원시 IP 주소 - 원시 IP 주소에서 또는 원시 IP 주소에 의해 수행된 활동을 검색할 수 있습니다. 원시 IP는 특정 시퀀스와 같거나 같지 않거나 특정 시퀀스로 시작하거나 시작하지 않을 수 있습니다. 
  - IP 범주 - 활동을 수행한 IP 주소 범주입니다(예: 관리 IP 주소 범위의 모든 활동). 범주는 관련 IP 주소를 포함하도록 구성해야 합니다. 단, 미리 구성되며 두 개의 IP 태그(Anonymous proxy 및 Tor)를 포함하는 “Risky”(위험) 범주는 예외입니다. IP 범주를 구성하는 방법을 알아보려면 [요구에 따라 데이터 구성](ip-tags.md)을 참조하세요.  
  - IP 태그 - 활동을 수행한 IP 주소의 태그입니다(예: 익명 프록시 IP 주소의 모든 활동). Cloud App Security는 구성할 수 없는 기본 제공 IP 태그의 집합을 만듭니다. 또한 자체 IP 태그를 구성할 수 있습니다. IP 태그 구성에 대한 자세한 내용은 [요구에 따라 데이터 구성](ip-tags.md)을 참조하세요.
  기본 제공 IP 태그는 다음과 같습니다.
  - Microsoft 앱(그중 14개)
  - 익명 프록시
  - 봇넷(특정 봇넷에 대한 세부 정보 링크를 통해 활동이 봇넷에 의해 수행되었는지 확인하게 됩니다.)
  - Darknet 검색 IP
  - 맬웨어 C&C 서버
  - 원격 연결 분석기
  - 위성 공급자
  - 스마트 프록시 및 액세스 프록시(고의로 제외)
  - Tor 종료 노드
  - Zscaler


- 가장된 활동 - 다른 사용자의 이름으로 수행된 활동만 검색합니다.  

- 인스턴스 - 활동이 수행되었거나 수행되지 않은 앱 인스턴스입니다.

- 위치 – 활동을 수행한 국가입니다.  

- 일치 정책 – 포털에 설정된 특정 정책에서 일치하는 활동을 검색합니다.  

- 등록된 ISP – 활동을 수행한 ISP입니다.

- 원본 - 활동이 검색된 원본을 기준으로 검색합니다. 원본은 다음 중 하나일 수 있습니다.
  - 앱 커넥터 - 앱의 API 커넥터에서 직접 가져오는 로그입니다.
  - 앱 커넥터 분석 - API 커넥터의 정보 검사를 기반으로 한 Cloud App Security 강화입니다.
  

- 사용자 – 활동을 수행한 사용자입니다. 도메인, 그룹, 이름 또는 조직을 기준으로 필터링할 수 있습니다. 특정 사용자 없이 활동을 필터링하려면 '설정되지 않음' 연산자를 사용할 수 있습니다.  
  - 사용자 도메인 - 특정 사용자 도메인을 검색합니다.
  - 사용자 조직 – 활동을 수행한 사용자의 조직 구성 단위(예: EMEA_marketing 사용자가 수행한 모든 활동).  
  - 사용자 그룹 – 연결된 앱에서 가져올 수 있는 특정 사용자 그룹(예: Office 365 관리자)입니다.  
  - 사용자 이름 - 특정 사용자 이름을 검색합니다. 특정 사용자 그룹의 사용자 목록을 보려면 **Activity drawer**(활동 서랍)에서 사용자 그룹의 이름을 클릭합니다. 클릭하면 그룹의 모든 사용자를 나열하는 [계정] 페이지로 이동됩니다. 여기에서 그룹의 특정 사용자에 대한 계정 정보로 다운할 수 있습니다.
    -  **사용자 그룹** 및 **사용자 이름** 필터를 추가로 필터링하려면 **As** 필터를 사용하여 다음 중 하나일 수 있는 사용자 역할을 선택합니다.
        - 활동 개체만 - 선택한 사용자 또는 사용자 그룹이 해당 활동을 수행하지 않았고 활동의 개체임을 나타냅니다.
        - 행위자만 - 사용자 또는 사용자 그룹이 활동을 수행했음을 나타냅니다.
        - 모든 역할 - 사용자 또는 사용자 그룹이 활동을 수행한 사람 또는 활동의 개체로 활동에 참여했음을 나타냅니다.

- 사용자 에이전트 – 활동을 수행한 사용자 에이전트입니다.  
  
- 사용자 에이전트 태그 – 기본 제공 사용자 에이전트 태그입니다(예: 오래된 브라우저 또는 오래된 운영 체제의 모든 활동).  

<!--
>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon](./media/clear-filters.png). -->


## <a name="activity-queries"></a>활동 쿼리

조사를 간소화하기 위해 사용자 지정 쿼리를 만들어서 나중에 사용할 수 있도록 저장할 수 있습니다. 

1. **활동 로그** 페이지에서 위의 설명대로 필터를 사용하여 필요에 따라 앱을 드릴다운합니다. 

2. 쿼리 빌드를 완료한 후 필터의 오른쪽 위 모서리에서 **다른 이름으로 저장** 단추를 클릭합니다. 

3. **쿼리 저장** 팝업에 쿼리 이름을 지정합니다.

   ![새 쿼리](./media/new-activity-query.png)

4. 나중에 쿼리를 사용하려면 **쿼리**에서 **저장된 쿼리**까지 아래로 스크롤하여 쿼리를 선택합니다. 

   ![쿼리 열기](./media/select-activity-query.png)


Cloud App Security는 **제안된 쿼리**도 제공합니다. 제안된 쿼리는 활동을 필터링하는 권장 조사 환경을 제공합니다. 이러한 쿼리를 편집하고 사용자 지정 쿼리로 저장할 수 있습니다. 다음은 선택 가능한 제안된 쿼리입니다.

 - 관리 활동 - 관리와 관련된 활동만 표시하도록 모든 활동을 필터링합니다.

 - 다운로드 활동 - 다운로드 활동(예: 사용자 목록을 .csv 파일로 다운로드, 공유 콘텐츠 다운로드 및 폴더 다운로드)인 활동만 표시하도록 모든 활동을 필터링합니다.

 - 실패한 로그인 - SSO를 통해 실패한 로그온 및 실패한 로그인만 표시하도록 모든 활동을 필터링합니다. 

 - 파일 및 폴더 활동 - 파일 및 폴더와 관련된 활동만 표시하도록 모든 활동을 필터링합니다. 필터에는 파일의 생성, 삭제, 업로드, 다운로드, 격리 및 액세스, 콘텐츠 전송과 함께 폴더 업로드, 다운로드 및 액세스가 포함됩니다. 

 - 가장 활동 - 가장 활동만 표시하도록 모든 활동을 필터링합니다.

 - 사서함 활동 - Microsoft Exchange Online 활동(예: 항목 만들기, 사서함의 메시지 제거, 메시지 업데이트 및 다른 이름으로 전송 권한(가장)을 사용하여 메시지 보내기)만 표시하도록 모든 활동을 필터링합니다.

 - 암호 변경 및 재설정 요청 - 암호 재설정, 암호 변경 및 다음 로그인 시 암호 강제 변경과 관련된 활동만 표시하도록 모든 활동을 필터링합니다.

 - 보안 위험 - DLP 정책과 일치하는 활동만 표시하도록 모든 활동을 필터링합니다.

 - 공유 활동 - 폴더 및 파일 공유와 관련된 활동(예: 회사 링크 만들기, 익명 링크 만들기 및 읽기/쓰기 권한 부여)만 표시하도록 모든 활동을 필터링합니다.

 - 성공적인 로그인 - 성공적인 로그인을 포함하는 활동(예: 가장한 동작, 가장한 로그온, Single Sign-On 로그온 및 새 디바이스에서 로그온)만 표시하도록 모든 활동을 필터링합니다.

![쿼리 활동](./media/queries-activity.png)
 
또한 제안된 쿼리를 새 쿼리의 시작점으로 사용할 수 있습니다. 먼저 제안된 쿼리 중 하나를 선택합니다. 그런 다음 필요한 내용을 변경하고 마지막으로 **다른 이름으로 저장**을 클릭하여 **저장된 쿼리**를 새로 만듭니다.


## <a name="next-steps"></a>다음 단계 
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

  
  
