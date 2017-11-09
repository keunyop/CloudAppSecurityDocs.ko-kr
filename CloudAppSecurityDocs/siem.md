---
title: "Cloud App Security와 SIEM 통합 | Microsoft 문서"
description: "이 항목에서는 SIEM과 Cloud App Security의 통합에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/5/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6abf7cbaf3f13bd84255846f3d2430a67a0db523
ms.sourcegitcommit: 2b8965381d94a5bb6349d8e25e1dc29b092a88b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2017
---
# <a name="siem-integration"></a>SIEM 통합
    
이제 Office 365 경고와 활동을 중앙에서 모니터링할 수 있도록 Cloud App Security를 SIEM 서버와 통합할 수 있습니다. 새 활동 및 이벤트가 Office 365에서 지원되므로 Cloud App Security에도 표시됩니다. SIEM 서비스와 통합하면 일반적인 보안 워크플로를 유지 관리하고, 보안 절차를 자동화하고, 클라우드 기반 이벤트와 온-프레미스 이벤트를 상호 연결하여 클라우드 응용 프로그램을 더 잘 보호할 수 있습니다. Cloud App Security SIEM 에이전트는 서버에서 실행되며 Cloud App Security에서 경고와 활동을 가져와서 SIEM 서버로 스트리밍합니다.

먼저 SIEM을 Cloud App Security와 통합하면 지난 2일 동안의 활동과 경고가 SIEM에 전달되고, 그 이후부터 모든 활동 및 경고(선택한 필터 기반)가 전달됩니다. 또한 장기간 이 기능을 사용하지 않도록 설정한 경우 다시 사용하도록 설정하면 지난 2일간의 경고와 활동을 전달한 다음 그 이후부터 모든 경고와 활동을 전달합니다.

## <a name="siem-integration-architecture"></a>SIEM 통합 아키텍처

SIEM 에이전트가 조직의 네트워크에 배포됩니다. 배포 및 구성되면 Cloud App Security RESTful API를 사용하여 구성된 데이터 유형(경고 및 활동)을 끌어옵니다.
그러면 트래픽이 포트 443의 암호화된 HTTPS 채널을 통해 전송됩니다.

SIEM 에이전트가 Cloud App Security에서 데이터를 검색하면 설정 중에 제공된 네트워크 구성(사용자 지정 포트가 있는 UDP 또는 TCP)을 사용하여 로컬 SIEM으로 Syslog 메시지를 전송합니다. 

![SIEM 통합 아키텍처](./media/siem-architecture.png)



## <a name="how-to-integrate"></a>통합 방법

SIEM과의 통합은 세 단계로 수행됩니다.
1. Cloud App Security 포털에서 설정합니다. 
2. JAR 파일을 다운로드하고 서버에서 실행합니다.
3. SIEM 에이전트가 제대로 작동하는지 확인합니다.

### <a name="prerequisites"></a>필수 구성 요소

- 표준 Windows 또는 Linux 서버(가상 컴퓨터일 수 있음).
- 서버에서 Java 8이 실행 중이어야 합니다. 이전 버전은 지원되지 않습니다.

## <a name="integrating-with-your-siem"></a>SIEM과 통합

### <a name="step-1-set-it-up-in-the-cloud-app-security-portal"></a>1단계: Cloud App Security 포털에서 설정합니다.

1. Cloud App Security 포털의 [설정] 코그 아래에서 **보안 확장**을 클릭하고 나서 **SIEM 에이전트** 탭을 클릭합니다.

2. 더하기 아이콘을 클릭하여 **SIEM 에이전트 추가** 마법사를 시작합니다.
3. 마법사에서 **Add SIEM agent**(SIEM 에이전트 추가)를 클릭합니다. 
4. 마법사에서 이름을 입력하고, **SIEM 형식을 선택**하고, 해당 형식과 관련된 **고급 설정**을 지정합니다. **다음**을 클릭합니다.

   ![일반 SIEM 설정](./media/siem1.png)

5. **원격 syslog 호스트**의 IP 주소 또는 호스트 이름과 **Syslog 포트 번호**를 입력합니다. 원격 Syslog 프로토콜로 TCP 또는 UDP를 선택합니다.
세부 정보가 없는 경우 보안 관리자와 작업하여 세부 정보를 가져올 수 있습니다.
**다음**을 클릭합니다.
  ![원격 Syslog 설정](./media/siem2.png)

6. SIEM 서버로 내보낼 데이터 형식, **경고** 및 **활동**을 선택합니다. 슬라이더를 사용하여 사용 여부를 설정합니다. 기본적으로 모든 항목이 선택되어 있습니다. **적용 대상** 드롭다운을 사용하여 특정 경고와 활동만 SIEM 서버로 보내도록 필터를 설정할 수 있습니다.
**Edit and preview results**(결과 편집 및 미리 보기)를 클릭하여 필터가 예상대로 작동하는지 확인할 수 있습니다. **다음**을 클릭합니다. 

  ![데이터 형식 설정](./media/siem3.png)

7. 토큰을 복사하고 나중을 위해 저장합니다. Finish(마침)를 클릭하고 마법사를 나와 SIEM 페이지로 돌아가면 추가한 SIEM 에이전트가 테이블에 표시됩니다. 나중에 연결될 때까지 **Created**(만들어짐) 상태로 표시됩니다.

### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>2단계: JAR 파일을 다운로드하고 서버에서 실행합니다.

1. [Microsoft 다운로드 센터에서 .zip 파일을 다운로드](https://go.microsoft.com/fwlink/?linkid=838596)하고 압축을 풉니다.

2. Zip 파일에서 .jar 파일을 추출하고 서버에서 실행합니다.
 파일을 실행한 후 다음을 실행합니다.
    
      java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
> [!NOTE]
> - 파일 이름은 SIEM 에이전트의 버전에 따라 달라질 수 있습니다.
> - 대괄호([ ]) 안에 있는 매개 변수는 선택 사항이며, 관련된 경우에만 사용해야 합니다.
> - 서버 시작 시 JAR을 실행하는 것이 좋습니다.
>   - Windows: 예약된 작업으로 실행하고, 작업을 **사용자가 로그온했는지 여부에 상관 없이 실행**으로 구성하고 **다음보다 더 오래 실행되면 작업 중지** 확인란을 선택 취소했는지 확인합니다.
>   - Linux: rc.local 파일에 **&**가 포함된 실행 명령을 추가합니다. 예를 들면 다음과 같습니다. `java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &`

여기서는 다음 변수가 사용됩니다.
- DIRNAME은 로컬 에이전트 디버그 로그에 사용할 디렉터리의 경로입니다.
- ADDRESS[:PORT]는 서버가 인터넷에 연결하는 데 사용하는 프록시 서버 주소 및 포트입니다.
- TOKEN은 이전 단계에서 복사한 SIEM 에이전트 토큰입니다.

언제든지 도움말을 보려면 -h를 입력할 수 있습니다.

다음은 SIEM에 전송된 샘플 활동 로그입니다.
```
    2017-07-11T19:14:55.895Z CEF:0|MCAS|SIEM_Agent|0.102.17|EVENT_CATEGORY_LOGIN|Log on|0|externalId=1499800495894_e453bc33-a7c1-48f7-8397-8ae8e2758183 start=1499800495895 end=1499800495895 msg=Log on suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online dvc=13.82.149.151 requestClientApplication=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36 machine_id_149980022970038514 cs1Label=portalURL cs1=https://cloud-app-security.com/#/audits?activity.id\=eq(1499800495894_e453bc33-a7c1-48f7-8397-8ae8e2758183,) cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=targetObjects cs3=admin@contoso.com c6a1Label="Device IPv6 Address" c6a1=
    2017-07-11T19:14:56.781Z CEF:0|MCAS|SIEM_Agent|0.102.17|EVENT_CATEGORY_DOWNLOAD_FILE|Download file|0|externalId=1499800496781_2e50118e-dee7-40d7-b912-b81a10feed28 start=1499800496781 end=1499800496781 msg=Download file: file name50280117yyct6t.xlsx suser=roy@adallom.com.test destinationServiceName=Salesforce dvc=13.82.149.151 requestClientApplication=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36 machine_id_149979855250880034 cs1Label=portalURL cs1=https://cloud-app-security/#/audits?activity.id\=eq(1499800496781_2e50118e-dee7-40d7-b912-b81a10feed28,) cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=targetObjects cs3=name50280117yyct6t.xlsx c6a1Label="Device IPv6 Address" c6a1=
    2017-07-11T19:16:04.666Z CEF:0|MCAS|SIEM_Agent|0.102.17|EVENT_CATEGORY_SSO_LOGIN|Single sign-on log on|0|externalId=1499800564666_06496600-edde-4d81-a995-7632e70fb24f start=1499800564666 end=1499800564666 msg=Single sign-on log on suser=admin@contoso.com destinationServiceName=Microsoft Online Services dvc=13.82.149.151 requestClientApplication=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36 machine_id_149980039637481908 cs1Label=portalURL cs1=https://cloud-app-security.com/#/audits?activity.id\=eq(1499800564666_06496600-edde-4d81-a995-7632e70fb24f,) cs2Label=uniqueServiceAppIds cs2=APPID_11394 cs3Label=targetObjects cs3=admin@contoso.com c6a1Label="Device IPv6 Address" c6a1=
    2017-07-12T13:28:29.067Z CEF:0|MCAS|SIEM_Agent|0.102.17|EVENT_CATEGORY_DOWNLOAD_FILE|Download file|0|externalId=1499866109067_8e3fae2c-ca5b-4163-84b6-fb9a03c4d052 start=1499866109067 end=1499866109067 msg=Download file: file CC004.txt suser=admin@box-contoso.com destinationServiceName=Box dvc=194.69.102.134 requestClientApplication=Mozilla/5.0 (Linux; Android 7.0; SAMSUNG SM-G930F Build/NRD90M) AppleWebKit/537.36 (KHTML, like Gecko) SamsungBrowser/5.0 Chrome/51.0.2704.106 Mobile Safari/537.36 cs1Label=portalURL cs1=https://cloud-app-security.com/#/audits?activity.id\=eq(1499866109067_8e3fae2c-ca5b-4163-84b6-fb9a03c4d052,) cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=targetObjects cs3=CC004.txt c6a1Label="Device IPv6 Address" c6a1=
    2017-07-12T14:15:33.901Z CEF:0|MCAS|SIEM_Agent|0.102.17|EVENT_CATEGORY_UPLOAD_FILE|Upload file|0|externalId=1499868933901_72c21ebe-c206-4d8c-a41b-224035868d09 start=1499868933901 end=1499868933901 msg=Upload file: file response.txt suser=user1@test15-adallom.com destinationServiceName=Google Drive dvc=194.69.102.134 requestClientApplication=Mozilla/5.0 (Windows NT 10.0; WOW64; Trident/7.0; Touch; rv:11.0) like Gecko cs1Label=portalURL cs1=https://cloud-app-security.com/#/audits?activity.id\=eq(1499868933901_72c21ebe-c206-4d8c-a41b-224035868d09,) cs2Label=uniqueServiceAppIds cs2=APPID_26069 cs3Label=targetObjects cs3=response.txt c6a1Label="Device IPv6 Address" c6a1=
    2017-07-12T18:53:16.519Z CEF:0|MCAS|SIEM_Agent|0.102.17|EVENT_CATEGORY_LOGIN|Log on|0|externalId=1499885596519_ed261269-9b07-4418-9ded-8cad464d677f start=1499885596519 end=1499885596519 msg=Log on suser=admin@contoso.com destinationServiceName=Office 365 dvc=13.82.149.151 requestClientApplication=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36 machine_id_149988543613557447 cs1Label=portalURL cs1=https://cloud-app-security.com/#/audits?activity.id\=eq(1499885596519_ed261269-9b07-4418-9ded-8cad464d677f,) cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=targetObjects cs3=admin@contoso.com c6a1Label="Device IPv6 Address" c6a1=
```
경고 로그 파일 예제도 있습니다.
```
  2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660
  2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349
  2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d
  2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8
  2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d
  2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3
```

### <a name="step-3-validate-that-the-siem-agent-is-working"></a>3단계: SIEM 에이전트가 제대로 작동하는지 확인합니다.

1. Cloud App Security 포털의 SIEM 에이전트 상태가 **연결 오류** 또는 **연결 끊김**이 아닌지, 에이전트 알림이 없는지를 확인합니다. 연결이 2시간 이상 동안 끊어진 경우 **연결 오류**로 표시되고, 12시간 이상 끊어진 경우 **연결 끊김**으로 표시됩니다.
 ![SIEM 연결 끊김](./media/siem-not-connected.png)
 
   대신 상태는 ![SIEM connected](./media/siem-connected.png)(SIEM 연결됨)와 같이 연결된 상태여야 합니다.

2. Syslog/SIEM 서버에서, Cloud App Security에서 오는 활동 및 경고가 표시되는지 확인합니다.


## <a name="regenerating-your-token"></a>토큰 다시 생성
토큰이 손실된 경우, 테이블에서 SIEM 에이전트에 대한 행의 끝에 있는 점 세 개를 클릭하고 **Regenerate token**(토큰 다시 생성)을 선택하여 언제든 토큰을 다시 생성할 수 있습니다.

 ![SIEM - 토큰 다시 생성](./media/siem-regenerate-token.png)

## <a name="editing-your-siem-agent"></a>SIEM 에이전트 편집 
나중에 SIEM 에이전트를 편집해야 하는 경우 테이블에서 SIEM 에이전트에 대한 행의 끝에 있는 점 세 개를 클릭하고 **Edit**(편집)을 선택합니다. SIEM 에이전트를 편집하는 경우 .jar 파일은 자동으로 업데이트되므로 다시 실행할 필요가 없습니다.

![SIEM - 편집](./media/siem-edit.png)

## <a name="deleting-your-siem-agent"></a>SIEM 에이전트 삭제
나중에 SIEM 에이전트를 삭제해야 하는 경우 테이블에서 SIEM 에이전트에 대한 행의 끝에 있는 점 세 개를 클릭하고 **Delete**(삭제)을 선택합니다.

![SIEM - 삭제](./media/siem-delete.png)

> [!NOTE]
> 이 기능은 공개 미리 보기로 제공됩니다.

## <a name="high-availability-options"></a>고가용성 옵션

SIEM 에이전트는 최대 2일의 가동 중지 시간 복구를 지원하는 단일 끝점입니다. 고객 끝점으로 부하 분산 장치를 사용하면 고가용성에 대한 추가 조치를 완수할 수 있습니다.

## <a name="see-also"></a>참고 항목  
[SIEM 통합 문제 해결](troubleshooting-siem.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  