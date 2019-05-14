---
title: API-Cloud App Security를 사용 하 여 활동 조사 | Microsoft Docs
description: 이 문서는 API를 사용 하 여 Cloud App Security에서 사용자 동작을 조사 하는 방법에 정보를 제공 합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 03/26/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 0f2f971d-10e3-496d-8004-96d9fad71cae
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: db4e10c7ecc8e82795d3a75fb915757bfada6bb9
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568287"
---
# <a name="investigate-activities-using-the-api"></a>API를 사용 하 여 활동 조사

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security를 완벽 하 게 지원 되는 REST API 서비스를 사용 하 여 프로그래밍 방식으로 상호 작용할 수를 제공 합니다.

연결 된 클라우드 앱에서 사용자가 수행한 활동 조사에 Microsoft Cloud App Security Api를 사용할 수 있습니다. 

Cloud App Security 활동 API 모드 검색 및 많은 양의 데이터 (5,000 명 이상의 활동)의 검색을 위해 최적화 됩니다. 모든 결과 검색 될 때까지 쿼리 활동 데이터를 반복적으로 검색 하는 API입니다. 

> [!NOTE] 
> 사용 하는 좋습니다 대량의 활동 및 대규모 배포에는 [SIEM 에이전트](siem.md) 활동 검색에 대 한 합니다.

**에 활동 검색 API를 사용 합니다.**

1. 데이터에서 쿼리를 실행 합니다.
1. 사용 하 여 반환 명령을 수행 하면 단일 검색에 나열 될 수 있는 보다 더 많은 레코드의 경우 `nextQueryFilters` 실행 해야 하는 합니다. 이 명령은 쿼리는 모든 결과 반환 될 때까지 검색 될 때마다 발생 합니다.
 
 
**요청 본문 매개 변수**:
- "필터": 필터는 요청에 대 한 모든 검색 필터를 사용 하 여 개체를 참조 하세요 [활동 필터](activity-filters.md) 자세한 내용은 합니다. 요청 제한, 쿼리에 대 한 제한이 포함 되었는지 확인 하지 않으려면 예를 들어, 마지막 날의 활동을 쿼리하거나 특정 앱을 필터링 합니다.
- "isScan": Boolean입니다. 검사 모드를 사용 하도록 설정 합니다.
- “sortDirection”: 정렬 방향을, 가능한 값은 "asc" 및 "desc" 
- “sortField”: 작업을 정렬 하는 데 사용 하는 필드입니다. 가능한 값은 
    - 날짜-발생 한 날짜 후 활동 (기본값임).
    - 생성 작업을 저장할 때 타임 스탬프입니다.
- "제한": 정수입니다. 500에서 5000 사이의 검색 모드 (기본값은 500). 모든 데이터를 검색에 사용 되는 반복 횟수를 제어 합니다. 

**응답 매개 변수**:
- "data": 반환된 된 데이터입니다. 사용 될 "제한" 레코드 개수까지 각 반복 합니다. 더 많은 레코드를 가져올 수 없으면 (hasNext = true), 마지막으로 모든 데이터를 한 번만 나열 되어 있는지 확인 하려면 몇 가지 레코드가 삭제 됩니다.
- "hasNext": Boolean입니다. 데이터에 다른 반복 필요한 지 여부를 나타냅니다.
- “nextQueryFilters”: 다른 반복 필요한 경우 연속 JSON 쿼리 실행 수를 포함 합니다. 다음 요청에서 "필터" 매개 변수로 사용 합니다.

다음 Python 예제에서는 Exchange Online에서 지난 날의 모든 활동을 가져옵니다.

      import requests
      import json
      ACTIVITIES_URL = 'https://<your_tenant>.portal.cloudappsecurity.com/api/v1/activities/'
    
      your_token = '<your_token>'
         headers = {
         'Authorization': 'Token {}'.format(your_token),
        }
    
        filters = {
          # optionally, edit to match your filters
          'date': {'gte_ndays': 1},
          'service': {'eq': [20893]}
        }
        request_data = {
         'filters': filters,
         'isScan': True
        }
        
        records = []
        has_next = True
        while has_next:
            content = json.loads(requests.post(ACTIVITIES_URL, json=request_data, headers=headers).content)
            response_data = content.get('data', [])
            records += response_data
            print('Got {} more records'.format(len(response_data)))
            has_next = content.get('hasNext', False)
            request_data['filters'] = content.get('nextQueryFilters')
        
        print('Got {} records in total'.format(len(records)))
        
 
## <a name="next-steps"></a>다음 단계
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
