---
title: Cloud Discovery 배포 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud Discovery 작업을 시작하기 위한 설정 절차에 대해 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 3/18/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 06668c75ad1629fb4047d353379a16c01c056632
ms.sourcegitcommit: fe4cd2174f6dc83811a2d484f079e8dfbac5d082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476640"
---
# <a name="set-up-cloud-discovery"></a>Cloud Discovery 설정

*적용 대상: Microsoft Cloud App Security*

Cloud Discovery는 16,000개 이상의 클라우드 앱이 포함된 Microsoft Cloud App Security 클라우드 앱 카탈로그에 대한 트래픽 로그를 분석합니다. 이 앱은 70개를 넘는 위험 요인을 기준으로 순위 및 점수를 매겨 클라우드 사용, 섀도 IT 및 위험 섀도 IT에 대한 지속적인 가시성을 제공합니다.

## <a name="snapshot-and-continuous-risk-assessment-reports"></a>스냅숏 및 연속 위험 평가 보고서 

두 가지 유형의 보고서를 생성할 수 있습니다. 

- **스냅숏 보고서** - 방화벽 및 프록시에서 수동으로 업로드하는 트래픽 로그 집합에 대한 임시 가시성을 제공합니다.

- **연속 보고서** - Cloud App Security를 사용하여 네트워크에서 전달되는 모든 로그를 분석합니다. 이러한 보고서는 모든 데이터에 대해 향상된 가시성을 제공하고 Machine Learning 변칙 검색 엔진이나 사용자가 정의한 사용자 지정 정책을 사용하여 비정상적인 사용을 자동으로 식별합니다. 이러한 보고서는 다음과 같은 방법으로 연결하여 만들 수 있습니다.

  - [Windows Defender ATP 통합](wdatp-integration.md): Cloud App Security는 Cloud Discovery 롤아웃을 간소화하고, Cloud Discovery 기능을 회사 네트워크 너머로 확장하고, 머신 기반 조사를 사용하기 위해 기본적으로 Windows Defender ATP(Advanced Threat Protection)와 통합됩니다.
  - [로그 수집기](discovery-docker.md): 로그 수집기를 사용하여 네트워크에서 로그 업로드를 쉽게 자동화할 수 있습니다. 로그 수집기는 네트워크에서 실행되며 Syslog 또는 FTP를 통해 로그를 받습니다.
  - [Zscaler 통합](zscaler-integration.md): Cloud App Security와 Zscaler를 모두 사용하는 경우 두 제품을 통합하여 보안 Cloud Discovery 환경을 향상할 수 있습니다. Cloud App Security와 Zscaler는 함께 Zscaler 포털에서 Cloud Discovery의 원활한 배포, 비사용 권한 앱의 자동 차단 및 위험 평가를 직접 제공합니다.
 - [iboss 통합](iboss-integration.md): Cloud App Security와 iboss를 모두 사용하는 경우 두 제품을 통합하여 보안 Cloud Discovery 환경을 향상할 수 있습니다. 함께 Cloud App Security 및 iboss 비 사용 권한 앱 및 위험 평가 iboss 포털에서 직접 차단 자동 Cloud Discovery의 원활한 배포를 제공 합니다.

## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>로그 프로세스 흐름: 원시 데이터에서 위험 평가로

위험 평가 생성 프로세스는 다음과 같은 단계로 구성됩니다. 이 프로세스는 처리되는 데이터의 양에 따라 몇 분에서 몇 시간이 걸립니다.  

- **업로드** - 네트워크의 웹 트래픽 로그가 포털에 업로드됩니다.  

- **구문 분석** – Cloud App Security에서 각 데이터 원본에 대한 전용 파서를 사용하여 트래픽 로그에서 트래픽 데이터를 구문 분석하고 추출합니다.  

- **분석** - 클라우드 앱 카탈로그를 기준으로 트래픽 데이터를 분석하여 16,000개를 넘는 클라우드 앱을 식별하고 해당 위험 점수를 평가합니다. 활성 사용자와 IP 주소도 분석의 일부로 식별됩니다.  

- **보고서 생성** - 로그 파일에서 추출된 데이터의 위험 평가 보고서가 생성됩니다.


>[!NOTE]
> 연속 보고서 데이터는 하루에 두 번 분석됩니다.



## 지원되는 방화벽 및 프록시 <a name="supported-firewalls-and-proxies"></a>

- Barracuda - Web App Firewall(W3C)
- Blue Coat Proxy SG - Access log(W3C)
- Check Point
- Cisco ASA Firewall(Cisco ASA Firewall의 경우 정보 수준을 6으로 설정해야 함)
- Cisco ASA with FirePOWER
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki – URL 로그
- Clavister NGFW(Syslog)
- Digital Arts i-FILTER
- Fortinet Fortigate
- iboss Secure Cloud Gateway
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway(W3C)
- Palo Alto series Firewall
- Sonicwall(이전의 Dell)
- Sophos SG
- Sophos XG
- Sophos Cyberoam
- Squid(Common)
- Squid(Native)
- Websense-Web Security Solutions-조 사용 상세 보고서 (CSV)
- Websense-Web Security Solutions-인터넷 활동 로그 (CEF)
- Zscaler

> [!NOTE]
> Cloud Discovery는 IPv4 및 IPv6 주소를 모두 지원합니다.

로그가 지원되지 않는 경우 **기타**를 **데이터 원본**으로 선택하고 업로드하려는 어플라이언스와 로그를 지정합니다. Cloud App Security 클라우드 분석가 팀에서 로그를 검토하고 로그 유형에 대한 지원이 추가되는 경우 알려줍니다. 또는 형식과 일치하는 사용자 지정 파서를 정의할 수 있습니다. 자세한 내용은 [사용자 지정 로그 파서 사용](custom-log-parser.md)을 참조하세요.


데이터 특성(공급업체 설명서 참조):


|                 데이터 원본                  |    대상 앱 URL    |    대상 앱 IP     |       Username       |      원본 IP       |    총 트래픽     |    업로드된 바이트    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |          아니요          |          아니요          |
|                  Blue Coat                   | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                  Checkpoint                  |          아니요          | <strong>예</strong> |          아니요          | <strong>예</strong> |          아니요          |          아니요          |
|              Cisco ASA(Syslog)              |          아니요          | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> |          아니요          |
|           Cisco ASA with FirePOWER           | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                  Cisco FWSM                  |          아니요          | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> |          아니요          |
|              Cisco Ironport WSA              | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                 Cisco Meraki                 | <strong>예</strong> | <strong>예</strong> |          아니요          | <strong>예</strong> |          아니요          |          아니요          |
|           Clavister NGFW(Syslog)            | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                SonicWall(이전의 Dell)                | <strong>예</strong> | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|            Digital Arts i-FILTER             | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                  Fortigate                   |          아니요          | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                 Juniper SRX                  |          아니요          | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                 Juniper SSG                  |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                  McAfee SWG                  | <strong>예</strong> |          아니요          |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                    MS TMG                    | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|              Palo Alto 네트워크              |          아니요          | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                    Sophos                    | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |          아니요          |
|                Squid(Common)                | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> |          아니요          | <strong>예</strong> |
|                Squid(Native)                | <strong>예</strong> |          아니요          | <strong>예</strong> | <strong>예</strong> |          아니요          | <strong>예</strong> |
| Websense - Investigative detail report(CSV) | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|    Websense - Internet activity log(CEF)    | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
|                   Zscaler                    | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> | <strong>예</strong> |
     


## <a name="next-steps"></a>다음 단계

[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[연속 보고서에 대한 자동 로그 업로드 구성](configure-automatic-log-upload-for-continuous-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)
