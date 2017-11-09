---
title: "Microsoft Cloud App Security를 사용하여 Cloud Discovery 배포 | Microsoft 문서"
description: "이 항목에서는 Cloud Discovery 작업을 시작하기 위한 설정 절차에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0fa9125b611574d4f4fafb18c8bc649de82b1ad6
ms.sourcegitcommit: 1c9ed4923cb6b761aebd13a6caa3a6605412419a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2017
---
# <a name="set-up-cloud-discovery"></a>Cloud Discovery 설정
Cloud Discovery는 60개를 넘는 위험 요인을 기준으로 순위 및 점수가 매겨진 클라우드 앱 15,000개 이상의 Cloud App Security 클라우드 앱 카탈로그에 비교해 트래픽 로그를 분석하여 조직에 제기된 클라우드 사용, 섀도 IT, 위험 섀도 IT를 지속해서 파악합니다.
 
## <a name="snapshot-and-continuous-risk-assessment-reports"></a>스냅숏 및 연속 위험 평가 보고서 

두 가지 유형의 보고서를 생성할 수 있습니다. 
- **스냅숏 보고서**는 방화벽 및 프록시에서 수동으로 업로드하는 트래픽 로그 집합에 대해 임시 가시성을 제공합니다.
 
- **연속 보고서**는 Cloud App Security의 로그 수집기를 사용하여 네트워크에서 전달되는 모든 로그를 분석합니다. 이러한 보고서는 모든 데이터에 대해 향상된 가시성을 제공하고 Machine Learning 변칙 검색 엔진이나 사용자가 정의한 사용자 지정 정책을 사용하여 비정상적인 사용을 자동으로 식별합니다.
 
## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>로그인 프로세스 흐름: 원시 데이터에서 위험 평가로  
위험 평가 생성 프로세스는 다음 단계로 구성되며 처리되는 데이터 크기에 따라 몇 분에서 몇 시간 정도 걸립니다.  
  
-   **업로드** - 네트워크의 웹 트래픽 로그가 포털에 업로드됩니다.  
  
-   **구문 분석** – Cloud App Security에서 각 데이터 원본에 대한 전용 파서를 사용하여 트래픽 로그에서 트래픽 데이터를 구문 분석하고 추출합니다.  
  
-   **분석** - 클라우드 앱 카탈로그를 기준으로 트래픽 데이터를 분석하여 15,000개를 넘는 클라우드 앱을 식별하고 해당 위험 점수를 평가합니다. 활성 사용자와 IP 주소도 분석의 일부로 식별됩니다.  
  
-   **보고서 생성** - 로그 파일에서 추출된 데이터의 위험 평가 보고서가 생성됩니다.   
 
 
>[!NOTE]
>- 연속 보고서 데이터는 하루에 두 번 분석됩니다.
>- 로그 수집기는 데이터가 업로드되기 전에 압축합니다. 로그 수집기의 아웃바운드 트래픽은 수신하는 트래픽 로그의 10% 크기가 됩니다. 
 
## <a name="using-traffic-logs-for-cloud-discovery"></a>Cloud Discovery에 트래픽 로그 사용
Cloud Discovery에서는 트래픽 로그의 데이터를 활용합니다. 로그가 더 자세할수록 더 명확하게 파악할 수 있습니다. Cloud Discovery에는 다음과 같은 특성이 있는 웹 트래픽 데이터가 필요합니다.
- 트랜잭션 날짜
- 원본 IP
- 원본 사용자 - 권장
- 대상 IP 주소
- 대상 URL **권장**(URL은 IP 주소보다 클라우드 앱 검색에 더 높은 정확도를 제공함)
- 총 데이터 양(데이터 정보는 매우 중요함)
- 업로드하거나 다운로드한 데이터 양(클라우드 앱의 사용 패턴에 대한 통찰력 제공)
- 수행된 작업(허용/차단)
 
Cloud Discovery에서는 로그에 포함되지 않은 특성을 표시하거나 분석할 수 없습니다.
예를 들어 **Cisco ASA Firewall** 표준 로그 형식에는 **트랜잭션별로 업로드된 바이트의 크기**나 **사용자 이름**이 포함되지 않고 **대상 URL**도 포함되지 않지만 대상 IP만 포함됩니다.
따라서 이러한 특성은 이러한 로그에 대한 Cloud Discovery 데이터에 표시되지 않으며 클라우드 앱에 대한 가시성이 제한됩니다. Cisco ASA Firewall의 경우 정보 수준을 6으로 설정해야 합니다. 
 

Cloud Discovery 보고서를 생성하려면 트래픽 로그가 다음 조건을 충족해야 합니다.
1.  데이터 원본이 지원됩니다(아래 목록 참조).
2.  로그 형식이 예상되는 표준 형식과 일치합니다(로그 도구로 업로드할 때 확인).
3.  이벤트가 90일 이상 오래되지 않았습니다.
4.  로그 파일이 유효하며 아웃바운드 트래픽 정보를 포함합니다.
 


## <a name="supported-firewalls-and-proxies"></a>지원되는 방화벽 및 프록시

- Barracuda - Web App Firewall(W3C)
- Blue Coat Proxy SG - Access log(W3C)
- Check Point
- Cisco ASA Firewall(Cisco ASA Firewall의 경우 정보 수준을 6으로 설정해야 함)
- Cisco ASA with FirePOWER
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki – URL 로그
- Clavister NGFW(Syslog)
- Dell Sonicwall
- Fortinet Fortigate
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway(W3C)
- Palo Alto series Firewall
- Sophos SG
- Sophos Cyberoam
- Squid(Common)
- Squid(Native)
- Websense - Web Security Solutions - Investigative detail report(CSV)
- Websense - Web Security Solutions - Internet activity log(CEF)
- Zscaler

> [!NOTE]
> Cloud Discovery는 IPv4 및 IPv6 주소를 모두 지원합니다.

로그가 지원되지 않는 경우 **데이터 원본**에서 **기타**를 선택하고 업로드하려는 어플라이언스 및 로그를 지정합니다. Cloud App Security 클라우드 분석가 팀에서 로그를 검토하고 로그 유형에 대한 지원이 추가되는 경우 알려줍니다. 또는 형식과 일치하는 사용자 지정 파서를 정의할 수 있습니다. 자세한 내용은 [사용자 지정 로그 파서 사용](custom-log-parser.md)을 참조하세요.


데이터 특성(공급업체 설명서 참조):

|데이터 원본|대상 앱 URL|대상 앱 IP|Username|원본 IP|총 트래픽|업로드된 바이트|
|----|----|----|-----|----|----|----|
|Barracuda|**예**|**예**|**예**|**예**|아니요|아니요|
|Blue Coat|**예**|아니요|**예**|**예**|**예**|**예**|
|Checkpoint|아니요|**예**|아니요|**예**|아니요|아니요|
|Cisco ASA|아니요|**예**|아니요|**예**|**예**|아니요|
|Cisco ASA with FirePOWER|**예**|**예**|**예**|**예**|**예**|**예**|
|Cisco FWSM|아니요|**예**|아니요|**예**|**예**|아니요|
|Cisco Ironport WSA|**예**|**예**|**예**|**예**|**예**|**예**|
|Cisco Meraki|**예**|**예**|아니요|**예**|아니요|아니요||Cisco Scansafe|**예**|아니요|**예**|**예**|**예**|**예**|
|Clavister NGFW(Syslog)|**예**|**예**|**예**|**예**|**예**|**예**|
|Dell SonicWall|**예**|**예**|아니요|**예**|**예**|**예**|
|Fortigate|아니요|**예**|아니요|**예**|**예**|**예**|
|Juniper SRX|아니요|**예**|아니요|**예**|**예**|**예**|
|Juniper SSG|아니요|**예**|아니요|**예**|**예**|**예**|
|McAfee SWG|**예**|아니요|아니요|**예**|**예**|**예**|
|MS TMG|**예**|아니요|**예**|**예**|**예**|**예**|
|Palo Alto 네트워크|**예**|**예**|**예**|**예**|**예**|**예**|
|Sophos|**예**|**예**|**예**|**예**|**예**|아니요|
|Squid(Common)|**예**|아니요|**예**|**예**|아니요|**예**|
|Squid(Native)|**예**|아니요|**예**|**예**|아니요|**예**|
|Websense - Investigative detail report(CSV)|**예**|**예**|**예**|**예**|**예**|**예**|
|Websense - Internet activity log(CEF)|**예**|**예**|**예**|**예**|**예**|**예**|
|Zscaler|**예**|**예**|**예**|**예**|**예**|**예**|



## <a name="see-also"></a>참고 항목
 
[Cloud Discovery 스냅숏 보고서 만들기](create-snapshot-cloud-discovery-reports.md)

[연속 보고서에 대한 자동 로그 업로드 구성](configure-automatic-log-upload-for-continuous-reports.md)

[Cloud Discovery 데이터 작업](working-with-cloud-discovery-data.md)