---
title: "거버넌스 로그 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security에서 수행할 수 있는 모든 거버넌스 작업을 나열하고 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3536c0a5-fa56-4931-9534-cc7cc4b4dfb0
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 052ca8e20e75fcae7687d17687d7dd1a645ae5e6


---

# <a name="governance-log"></a>거버넌스 로그
거버넌스 로그는 수동 작업 및 자동 작업을 포함하여 Cloud App Security에서 실행하도록 설정한 각 작업에 대한 상태 레코드를 제공합니다. 이러한 작업에는 정책에서 설정한 작업, 파일 및 사용자에 대해 설정한 거버넌스 작업 및 Cloud App Security에서 수행하도록 설정한 다른 모든 작업이 포함됩니다. 또한 거버넌스 로그는 이러한 작업의 성공 또는 실패에 대한 정보를 제공합니다. 거버넌스 로그에서 일부 거버넌스 작업을 다시 시도하거나 되돌리도록 선택할 수 있습니다. 

다음은 클라우드 Cloud App Security 포털을 사용하여 수행할 수 있는 작업의 전체 목록입니다. 이러한 작업은 **위치** 열에 설명된 대로 콘솔 전체의 다양한 위치에서 사용하도록 설정됩니다. 수행된 각 거버넌스 작업은 거버넌스 로그에 나열됩니다.
정책 충돌이 있을 경우 거버넌스 작업을 처리하는 방법에 대한 자세한 내용은 [정책 충돌](control-cloud-apps-with-policies.md)을 참조하세요. 

**위치**|**대상 개체 유형**|**거버넌스 작업**|**설명**|**관련된 커넥터** 
---------|---------|---------|---------|---------
|파일 정책|파일|협력자로만 제한|명명된 협력자만 파일에 액세스할 수 있습니다.|상자|
|설정 > 클라우드 검색 설정 |클라우드 검색|클라우드 검색 점수 다시 계산|점수 메트릭 변경 후 클라우드 앱 카탈로그에서 점수를 다시 계산합니다.|검색|
|설정 > 클라우드 검색 설정 > 데이터 뷰 관리|클라우드 검색|사용자 지정 클라우드 검색 필터 데이터 뷰 만들기|검색 결과를 더 세부적으로 보기 위한 새로운 데이터 뷰를 만듭니다. 예: 특정 IP 범위.|검색|
|검색 > 검색된 앱/IP 주소/사용자|클라우드 검색|검색 데이터 내보내기|검색 데이터에서 CSV를 만듭니다.|검색|
|설정 > 클라우드 검색 설정 > 데이터 삭제|클라우드 검색|클라우드 검색 데이터 삭제|검색 원본에서 수집된 모든 데이터를 삭제합니다.|검색|
|설정 > 클라우드 검색 설정 > 수동으로 로그 업로드/자동으로 로그 업로드|클라우드 검색|클라우드 검색 데이터 구문 분석|모든 로그 데이터가 구문 분석되었다는 알림입니다.|검색|
|조사 > 파일 및 파일 정책|파일|도메인에 읽기 권한 부여|전체 도메인의 지정된 도메인 또는 특정 도메인에 파일에 대한 읽기 권한을 부여합니다. 이 작업은 도메인에 대해 작업해야 하는 사용자의 도메인에 액세스 권한을 부여한 후 공용 액세스를 제거하려는 경우 유용합니다.|Google Apps|
|조사 > 파일|파일|자신에게 읽기 권한 부여|파일에 액세스하여 파일에 위반이 있는지를 파악할 수 있도록 자신에게 파일에 대한 읽기 권한을 부여합니다.|Google Apps|
|파일 정책 및 활동 정책|파일, 활동|사용자에게 알림|사용자가 수행한 활동이나 사용자가 소유한 파일이 정책을 위반한다는 사실을 알리기 위해 사용자에게 메일을 보냅니다. 위반 사실이 무엇이었는지 사용자가 알 수 있도록 사용자 지정 알림을 추가할 수 있습니다.|모두|
|파일 정책 및 조사 > 파일|파일|편집자의 공유 권한 제거|Google 드라이브에서 파일의 기본 편집자 권한은 공유도 허용합니다. 이 거버넌스 작업은 이 옵션을 제한하고 파일 공유를 소유자로 제한합니다.|Google Apps|
|조사 > 파일 및 파일 정책|파일|사용자 격리에 넣기|파일에서 모든 사용 권한을 제거하고 사용자의 루트 드라이브 아래에 있는 격리 폴더로 파일을 이동합니다. 이렇게 하면 사용자가 파일을 검토하고 이동할 수 있습니다. 수동으로 다시 이동할 경우 파일 공유가 복원되지 않습니다.|Box, OneDrive, SharePoint|
|파일 정책 및 조사 > 파일|파일|관리자 격리에 넣기|파일에서 모든 사용 권한을 제거하고 사용자의 루트 드라이브 아래에 있는 격리 폴더로 파일을 이동합니다. 이렇게 하면 관리자가 파일을 검토하고 이동할 수 있습니다.|상자|
|조사 > 파일 및 파일 정책|파일|협력자 제거|파일에서 특정 협력자를 제거합니다.|Google Apps, Box, OneDrive, SharePoint|
|조사 > 파일 및 파일 정책|파일|비공개로 만들기|파일을 비공개로 만들어 누구와도 공유하지 않는 협력자 또는 공개 링크를 더 이상 두지 않아도 됩니다.|Google Apps, OneDrive, SharePoint|
|조사 > 파일 및 파일 정책|파일|외부 사용자 제거|설정에서 내부로 구성된 도메인의 외부에 있는 모든 외부 협력자를 제거합니다.|Google Apps, Box |
|계정|파일|사용자의 공동 작업 제거|퇴사하는 사용자의 경우에 적합하도록 모든 파일에 대한 특정 사용자의 공동 작업을 모두 제거합니다.|Box, Google Apps|
|조사 > 파일 및 파일 정책|파일|공용 액세스 제거|파일이 사용자의 소유였고 파일을 공용 액세스 상태로 설정한 경우 파일에 부여된 액세스 권한 종류에 따라 파일에 대한 액세스 권한이 있는, 구성된 그 밖의 사용자만 해당 파일에 액세스할 수 있게 됩니다. |Google Apps|
|조사 > 파일 및 파일 정책|파일|직접 공유 링크 제거|공개 링크이지만 특정 사용자와만 공유되는, 파일에 대해 만들어진 링크를 제거합니다.|상자|
|앱 대시보드 > 앱 사용 권한|사용 권한|앱 금지|Google 및 Salesforce: Google 또는 Salesforce에 대한 타사 앱의 사용 권한을 철회하고 나중에 사용 권한을 받을 수 없도록 금지합니다. Office 365: Office에 대한 타사 앱의 액세스 권한을 허용하지 않지만 앱을 철회하지는 않습니다.|Google Apps, Salesforce, Office|
|앱 대시보드 > 앱 사용 권한|사용 권한|앱 금지 취소|Google 및 Salesforce: 앱에서 금지를 제거하고 사용자가 Google 또는 Salesforce를 사용하여 타사 앱에 사용 권한을 부여하도록 허용합니다. Office 365: Office에 대한 타사 앱의 사용 권한을 복원합니다.|Google Apps, Salesforce, Office|
|앱 대시보드 > 앱 사용 권한|사용 권한|앱 철회|Google, Salesforce 또는 Office에 대한 타사 앱의 사용 권한을 철회합니다. 이는 기존의 모든 사용 권한에 대해 수행되는 일회성 작업이지만 이후 연결을 차단하지는 않습니다. |Google Apps, Salesforce, Office|
|앱 대시보드 > 앱 사용 권한|계정|앱에서 사용자 철회|사용자 아래에 있는 번호를 클릭하면 특정 사용자를 철회할 수 있습니다. 화면에 특정 사용자가 표시되며 X를 사용하여 원하는 사용자의 사용 권한을 삭제할 수 있습니다.|Google Apps, Salesforce, Office|
|활동 정책 및 조사 > 계정|파일|암호 철회|사용자 계정의 암호를 철회합니다. 예를 들어 실패한 로그인 시도 횟수가 10번이 되면 암호를 철회하는 활동 정책을 설정합니다.|Google Apps|
|활동 정책 및 조사 > 계정|파일|관리자 권한 철회|관리자 계정의 권한을 철회합니다. 예를 들어 실패한 로그인 시도 횟수가 10번이 되면 관리자 권한을 철회하는 활동 정책을 설정합니다.|Google Apps|
|조사 > 파일|파일|내 자신의 읽기 권한 철회|내 자신의 파일에 대한 읽기 권한을 철회하며, 이 작업은 파일에 위반이 있는지를 파악하기 위해 자신에게 사용 권한을 부여한 후에 유용합니다.|Google Apps|
|조사 > 계정 및 정책|계정|사용자 일시 중단|사용자에게 액세스 권한과 로그인 권한이 없도록 설정합니다. 사용자가 로그인한 경우 이 작업이 설정되면 사용자가 즉시 잠깁니다.|Google Apps, Box, Office|
|파일 페이지 및 정책|파일|파일 소유권 이전|소유자를 변경합니다. 정책에서 특정 소유자를 선택합니다.|Google Apps|
|조사 > 계정 |파일|모든 파일 소유권 이전|계정에서 한 사용자의 모든 파일을 선택한 새 사용자가 소유하도록 이전합니다. 이전 소유자는 편집자가 됩니다. 소유권을 이전하고 나면 admin@gtest1.adallom.com이 편집자가 되며 더 이상 공유 설정을 변경할 수 없게 됩니다. 새 소유자는 소유권 변경에 대한 메일 알림을 받게 됩니다.|Google Apps|
|파일 정책|파일|휴지통|파일을 사용자의 휴지통에 넣습니다.|OneDrive, SharePoint|
|조사 > 계정|계정|사용자 일시 중단 해제|사용자 일시 중단을 해제합니다.|Google Apps, Box, Office|
|조사 > 파일|파일|사용자 격리에서 복원|사용자를 격리 상태에서 복원합니다.|상자|
|조사 > 계정|계정|계정 설정|특정 앱의 계정 설정 페이지(예: Salesforce 내부)로 이동합니다.|모든 앱(OneDrive 및 SharePoint) 설정은 Office 내에서 구성합니다.|
|조사 > 파일|파일|편집자에게 공유 허용|Google Drive에서 파일의 기본 편집자 권한은 공유도 허용합니다. 이 거버넌스 작업은 편집자의 공유 권한 제거와 반대이며, 편집자가 파일을 공유할 수 있도록 합니다.|Google Apps|
|파일 정책, 활동 정책|파일, 활동|마지막 파일 편집자에게 알림|마지막으로 파일을 편집한 사용자에게 해당 파일이 정책을 위반한다는 사실을 알리기 위해 메일을 보냅니다.|Google Apps, Box|
|파일 정책, 활동 정책|파일, 활동|파일 소유자에게 알림|파일이 정책을 위반하는 경우 파일 소유자에게 메일을 보냅니다(해당 관리자를 메일 참조에 포함하는 옵션이 있음). Dropbox에서는 소유자가 파일과 연결되지 않은 경우 설정된 특정 사용자에게 알림이 전송됩니다.|모든 앱|
|파일 정책, 활동 정책|파일, 활동|소유자의 관리자를 메일 참조에 포함|파일 소유자가 해당 파일이 정책을 위반한 상태라는 메일 알림을 받으면 이 작업에서는 선택적으로 파일 소유자의 관리자에게도 알립니다.|ServiceNow를 제외한 모든 앱|
|파일 정책, 활동 정책|파일, 활동|특정 사용자에게 알림|특정 사용자에게 정책을 위반하는 파일에 대해 알리기 위해 메일을 보냅니다.|모든 앱|

## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->

