---
title: "Cloud App Security와 SIEM 통합 | Microsoft 문서"
description: "이 항목에서는 SIEM과 Cloud App Security의 통합에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/1/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 866e9bcd9d9526d077365e4e4462567b20e3302f
ms.sourcegitcommit: 80d9396833957429cf4fe178f336ab2e1793069e
translationtype: HT
---
# <a name="siem-integration--public-preview-"></a>SIEM 통합 -공개 미리 보기- 
    
이제 경고와 활동을 중앙에서 모니터링할 수 있도록 Cloud App Security를 SIEM 서버와 통합할 수 있습니다. SIEM 서비스와 통합하면 일반적인 보안 워크플로를 유지 관리하고, 보안 절차를 자동화하고, 클라우드 기반 이벤트와 온-프레미스 이벤트를 상호 연결하여 클라우드 응용 프로그램을 더 잘 보호할 수 있습니다. Cloud App Security SIEM 에이전트는 서버에서 실행되며 Cloud App Security에서 경고와 활동을 가져와서 SIEM 서버로 스트리밍합니다.

먼저 SIEM을 Cloud App Security와 통합하면 지난&2;일 동안의 활동과 경고가 SIEM에 전달되고, 그 이후부터 모든 활동 및 경고(선택한 필터 기반)가 전달됩니다. 또한 장기간 이 기능을 사용하지 않도록 설정한 경우 다시 사용하도록 설정하면 지난&2;일간의 경고와 활동을 전달한 다음 그 이후부터 모든 경고와 활동을 전달합니다.

SIEM과의 통합은 세 단계로 수행됩니다.
1. Cloud App Security 포털에서 설정합니다. 
2. JAR 파일을 다운로드하고 서버에서 실행합니다.
3. SIEM 에이전트가 제대로 작동하는지 확인합니다.

## <a name="prerequisites"></a>필수 구성 요소

- 표준 Windows 또는 Linux 서버(가상 컴퓨터일 수 있음).
- 서버에서 Java 8이 실행 중이어야 합니다. 이전 버전은 지원되지 않습니다.

## <a name="integrating-with-your-siem"></a>SIEM과 통합

### <a name="step-1-set-it-up-in-the-cloud-app-security-portal"></a>1단계: Cloud App Security 포털에서 설정합니다.

1. Cloud App Security 포털의 Settings(설정) 코그 아래에서 **SIEM agents**(SIEM 에이전트)를 클릭합니다.

2. Add SIEM agent(SIEM 에이전트 추가)를 클릭하여 마법사를 시작합니다.
3. 마법사에서 **Add SIEM agent**(SIEM 에이전트 추가)를 클릭합니다.    
4. 마법사에서 이름을 입력하고, **SIEM 형식을 선택**하고, 해당 형식과 관련된 **고급 설정**을 지정합니다. **다음**을 클릭합니다.

   ![일반 SIEM 설정](./media/siem1.png)

5. **원격 syslog 호스트**의 IP 주소 및 **Syslog 포트 번호**를 입력합니다. 원격 Syslog 프로토콜로 TCP 또는 UDP를 선택합니다.
세부 정보가 없는 경우 보안 관리자와 작업하여 세부 정보를 가져올 수 있습니다.
**다음**을 클릭합니다.
  ![원격 Syslog 설정](./media/siem2.png)

6. SIEM 서버로 내보낼 데이터 형식, **경고** 및 **활동**을 선택합니다. 슬라이더를 사용하여 사용 여부를 설정합니다. 기본적으로 모든 항목이 선택되어 있습니다. **Apply to**(적용 대상) 드롭다운을 사용하여 특정 경고와 활동만 SIEM 서버로 보내도록 필터를 설정할 수 있습니다.
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
> - 대괄호 안에 있는 매개 변수는 선택 사항이며, 관련된 경우에만 사용해야 합니다.

여기서는 다음 변수가 사용됩니다.
- DIRNAME은 로컬 에이전트 디버그 로그에 사용할 디렉터리의 경로입니다.
- ADDRESS[:PORT]는 서버가 인터넷에 연결하는 데 사용하는 프록시 서버 주소 및 포트입니다.
- TOKEN은 이전 단계에서 복사한 SIEM 에이전트 토큰입니다.

언제든지 도움말을 보려면 -h를 입력할 수 있습니다.



### <a name="step-3-validate-that-the-siem-agent-is-working"></a>3단계: SIEM 에이전트가 제대로 작동하는지 확인합니다.

1. Cloud App Security 포털의 SIEM 에이전트 상태가 **연결 오류** 또는 **연결 끊김**이 아닌지, 에이전트 알림이 없는지를 확인합니다. 연결이 2시간 이상 동안 끊어진 경우 **연결 오류**로 표시되고, 12시간 이상 끊어진 경우 **연결 끊김**으로 표시됩니다.
 ![SIEM 연결 끊김](./media/siem-not-connected.png)
 
   대신 상태는  ![SIEM connected](./media/siem-connected.png)(SIEM 연결됨)와 같이 연결된 상태여야 합니다.

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

## <a name="troubleshooting-the-siem-agent"></a>SIEM 에이전트 문제 해결

Cloud App Security 포털의 SIEM 에이전트 상태가 **연결 오류** 또는 **연결 끊김**이 아닌지, 에이전트 알림이 없는지를 확인합니다. 연결이 2시간 이상 동안 끊어진 경우 **연결 오류**로 표시되고, 12시간 이상 끊어진 경우 **연결 끊김**으로 표시됩니다.

에이전트를 실행하는 동안 cmd 프롬프트에 다음 오류 중 하나가 표시되는 경우 다음 단계를 사용하여 문제를 해결하세요.

|Error|설명|해결 방법|
|----|----|----|
|부트스트랩 중 일반 오류 발생|에이전트 부트스트랩 중 예기치 않은 오류가 발생했습니다.|지원 담당자에게 문의하세요.|
|너무 많은 중요한 오류 발생|콘솔을 연결하는 동안 너무 많은 중요한 오류가 발생했습니다. 종료합니다.|지원 담당자에게 문의하세요.|
|잘못된 토큰|제공된 토큰이 잘못되었습니다.|올바른 토큰을 복사했는지 확인합니다. 위 프로세스를 사용하여 토큰을 다시 생성할 수 있습니다.|
|잘못된 프록시 주소|제공된 프록시 주소가 잘못되었습니다.|올바른 프록시 및 포트를 입력했는지 확인합니다.|


에이전트를 만든 후, Cloud App Security 포털의 SIEM 에이전트 페이지에 다음 **에이전트 알림** 중 하나가 표시되는 경우 다음 단계를 사용하여 문제를 해결하세요.

|Error|설명|해결 방법|
|----|----|----|
|**내부 오류**|SIEM 에이전트에 알 수 없는 오류가 발생했습니다.|지원 담당자에게 문의하세요.|
|**데이터 서버 보내기 오류**|TCP를 통해 Syslog 서버와 작업하는 경우 이 오류가 발생할 수 있습니다. SIEM 에이전트가 Syslog 서버에 연결할 수 없습니다.  이 오류가 표시되면 에이전트는 문제가 수정될 때까지 새 활동을 끌어오지 않습니다. 따라서 오류가 나타나지 않을 때까지 다음 문제 해결 단계를 수행하세요.|1. Syslog 서버를 올바르게 정의했는지 확인합니다. Cloud App Security UI에서 위에 설명된 대로 SIEM 에이전트를 편집하고, 서버 이름이 올바른지 확인하고, 정확한 포트를 설정합니다. </br>2. Syslog 서버에 대한 연결을 확인합니다. 방화벽이 통신을 차단하지 않는지 확인합니다.| 
|**데이터 서버 연결 오류**| TCP를 통해 Syslog 서버와 작업하는 경우 이 오류가 발생할 수 있습니다. SIEM 에이전트가 Syslog 서버에 연결할 수 없습니다.  이 오류가 표시되면 에이전트는 문제가 수정될 때까지 새 활동을 끌어오지 않습니다. 따라서 오류가 나타나지 않을 때까지 다음 문제 해결 단계를 수행하세요.|1. Syslog 서버를 올바르게 정의했는지 확인합니다. Cloud App Security UI에서 위에 설명된 대로 SIEM 에이전트를 편집하고, 서버 이름이 올바른지 확인하고, 정확한 포트를 설정합니다. </br>2. Syslog 서버에 대한 연결을 확인합니다. 방화벽이 통신을 차단하지 않는지 확인합니다.|
|**SIEM 에이전트 오류**|SIEM 에이전트의 연결이 X시간 이상 끊어졌습니다.|Cloud App Security 포털에서 SIEM 구성을 변경하지 않았는지 확인하세요. 변경하지 않은 경우 Cloud App Security와 SIEM을 실행 중인 컴퓨터 간의 연결 문제를 나타낼 수 있습니다.|
|**SIEM 에이전트 알림 오류**|SIEM 에이전트에서 SIEM 에이전트 알림 전달 오류가 발생했습니다.|SIEM 에이전트와 SIEM 서버 간 연결과 관련된 오류가 발생했음을 나타냅니다. SIEM 서버나 SIEM 에이전트를 실행 중인 컴퓨터를 차단하는 방화벽이 없는지 확인하세요. 또한 SIEM 서버의 IP 주소가 변경되지 않았는지 확인하세요.|

## <a name="see-also"></a>참고 항목  
[사용자 활동 정책](user-activity-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  