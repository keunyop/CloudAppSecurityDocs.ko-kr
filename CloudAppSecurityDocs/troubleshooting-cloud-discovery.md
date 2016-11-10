---
title: "Cloud Discovery 문제 해결 | Microsoft 문서"
description: "이 항목에서는 Cloud Discovery에서 자주 발생하는 오류 목록 및 각각에 대한 권장 해결 방법을 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 76dfaebb-d477-4bdb-b3d7-04cc3fe6431d
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 2d0b2cebdfa15cccc5888660da498446d620b64f


---

# <a name="troubleshooting-cloud-discovery"></a>Cloud Discovery 문제 해결
## <a name="log-parsing-errors"></a>로그 구문 분석 오류

거버넌스 로그를 사용하여 Cloud Discovery 로그 처리를 추적할 수 있습니다. 이 가이드에서는 표시될 수 있는 각 오류에 대해 수행할 해결 방법을 제공합니다.

### <a name="governance-log-errors"></a>거버넌스 로그 오류
|오류|설명|해결 방법|
|----|----|----|
|지원되지 않는 파일 형식|업로드된 파일이 유효한 로그 파일이 아닙니다(예: 이미지 파일).|방화벽 또는 프록시에서 직접 내보낸 **텍스트**, **zip** 또는 **gzip** 파일을 업로드하세요.|
|내부 오류|내부 리소스 오류가 감지되었습니다.|**다시 시도**를 클릭하여 작업을 다시 실행하세요.|
|로그 형식이 일치하지 않음|업로드한 로그 형식이 이 데이터 원본에 예상되는 로그 형식과 일치하지 않습니다.|1. 로그가 손상되지 않았는지 확인합니다. <br /> 2. 업로드 페이지에 표시된 샘플 형식과 로그를 비교하여 일치시킵니다.|
|트랜잭션이 90일 이상 오래됨|모든 트랜잭션이 90일 이상 오래되어 무시됩니다.|최근 이벤트와 함께 새 로그를 내보내고 다시 업로드하세요.|
|카탈로그된 클라우드 앱에 대한 트랜잭션 없음|모든 인식된 클라우드 앱에 대한 트랜잭션이 로그에 없습니다.|로그에 아웃바운드 트래픽 정보가 포함되어 있는지 확인하세요.|
|지원되지 않는 로그 유형|**데이터 원본 = 기타(지원되지 않음)**를 선택하면 로그가 구문 분석되지 않습니다. 대신 검토를 위해 Cloud App Security 기술 팀에 전송됩니다.|Cloud App Security 기술 팀은 각 데이터 원본마다 전용 파서를 작성합니다. 가장 많이 사용되는 데이터 원본은 [이미 지원](set-up-cloud-discovery.md)되고 있습니다. 지원되지 않는 데이터 원본의 각 업로드를 검토하고 새 데이터 원본 파서에 대한 파이프라인에 추가합니다. 새 파서 알림은 Cloud App Security 릴리스 정보의 일부로 게시됩니다.|
## <a name="log-collector-errors"></a>로그 수집기 오류

|문제|해결 방법|
|----|----|
|FTP를 통해 로그 수집기에 연결할 수 없습니다.|1. SSH 자격 증명이 아니라 FTP 자격 증명을 사용하고 있는지 확인합니다. <br />2. 사용 중인 FTP 클라이언트가 SFTP로 설정되지 않았는지 확인합니다.|
|수집기 구성을 업데이트하지 못했습니다.|1. 최신 액세스 토큰을 입력했는지 확인합니다. <br />2. 로그 수집기가 포트 443에서 아웃바운드 트래픽을 시작하도록 허용되는지 방화벽에서 확인합니다.|
|수집기로 전송된 로그가 포털에 표시되지 않습니다.|1.  거버넌스 로그에서 실패한 구문 분석 작업이 있는지 확인합니다.  <br />  &nbsp;&nbsp;&nbsp;&nbsp;그렇다면 위의 로그 구문 분석 오류 표를 사용하여 오류를 해결합니다.<br /> 2. 그렇지 않을 경우 포털에서 데이터 원본 및 로그 수집기 구성을 확인합니다. <br /> &nbsp;&nbsp;&nbsp;&nbsp;a. 데이터 원본 페이지에서 사용 중인 데이터 원본이 정확하게 구성되었는지 확인합니다. <br />&nbsp;&nbsp;&nbsp;&nbsp;b. 로그 수집기 페이지에서 데이터 원본이 올바른 로그 수집기에 연결되어 있는지 확인합니다. <br /> 3. 온-프레미스 로그 수집기 컴퓨터의 로컬 구성을 확인합니다.  <br />&nbsp;&nbsp;&nbsp;&nbsp;a. SSH를 통해 로그 수집기에 로그인하고 collector_config 유틸리티를 실행합니다.<br/>&nbsp;&nbsp;&nbsp;&nbsp;b. 방화벽 또는 프록시가 정의한 프로토콜(Syslog/TCP, Syslog/UDP 또는 FTP)을 사용하여 로그를 로그 수집기로 보내고 있는지, 올바른 포트 및 디렉터리로 보내고 있는지 확인합니다.<br /> &nbsp;&nbsp;&nbsp;&nbsp;c. 컴퓨터에서 netstat를 실행하고 방화벽 또는 프록시에서 들어오는 연결을 받는지 확인합니다. <br /> 4.   로그 수집기가 포트 443에서 아웃바운드 트래픽을 시작하도록 허용되는지 확인합니다.|

## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


