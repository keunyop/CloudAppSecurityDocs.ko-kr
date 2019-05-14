---
title: 네트워크 요구 사항 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 Cloud App Security를 사용하기 위해 열어야 하는 IP 주소와 포트에 대해 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 3/17/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 5602e0141b8c9251c0d76d4960361fbea62fb289
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568677"
---
# <a name="network-requirements"></a>네트워크 요구 사항

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 Microsoft Cloud App Security를 사용하기 위해 허용해야 하는 포트 및 IP 주소 목록과 허용 목록을 제공합니다. 

## <a name="view-your-data-center"></a>데이터 센터 보기

아래 요구 사항 중 일부는 연결되어 있는 데이터 센터에 따라 다릅니다. 

연결할 데이터 센터를 확인하려면 다음 단계를 수행합니다.

1. Cloud App Security 포털의 메뉴 모음에서 **물음표 아이콘**을 클릭합니다. 그런 다음, **정보**를 선택합니다. 

    ![정보 클릭](./media/about-menu.png)

2. Cloud App Security 버전 화면에서 지역 및 데이터 센터를 확인할 수 있습니다.

    ![데이터 센터 보기](./media/data-center.png)

## <a name="portal-access"></a>포털 액세스

Cloud App Security 포털에 액세스하려면 다음 IP 주소 및 DNS 이름에 대한 **아웃바운드 포트 443**을 방화벽의 허용 목록에 추가합니다.  

    portal.cloudappsecurity.com
    *.portal.cloudappsecurity.com
    cdn.cloudappsecurity.com
    https://adaproddiscovery.azureedge.net 
    *.s-microsoft.com
    *.msecnd.net
    dev.virtualearth.net
    *.cloudappsecurity.com
    flow.microsoft.com
    static2.sharepointonline.com
    dc.services.visualstudio.com
    *.blob.core.windows.net

또한 사용하는 데이터 센터에 따라 다음 항목을 허용 목록에 추가해야 합니다.
> [!div class="mx-tableFixed"]
> 
> |데이터 센터|IP 주소|DNS 이름|
> |----|----|----|
> |US1|13.80.125.22<br></br>52.183.75.62<br></br>13.91.91.243|\*.us.portal.cloudappsecurity.com|
> |US2|13.80.125.22<br></br>52.183.75.62<br></br>52.184.165.82|\*.us2.portal.cloudappsecurity.com<br></br>|
> |US3|13.80.125.22<br></br>52.183.75.62<br></br>40.90.218.198<br></br>40.90.218.196|*.us3.portal.cloudappsecurity.com<br></br>|
> |EU1|13.80.125.22<br></br>52.183.75.62<br></br>52.174.56.180|\*.eu.portal.cloudappsecurity.com<|
> |EU2|13.80.125.22<br></br>52.183.75.62<br></br>40.81.156.154<br></br>40.81.156.156|*.eu2.portal.cloudappsecurity.com|


> 
> [!NOTE]
> 와일드 카드(\*) 대신 특정 테넌트 URL만 열 수 있습니다. 예를 들어 위의 스크린샷에 따라 mod244533.us.portal.cloudappsecurity.com을 열 수 있습니다.

## <a name="siem-agent-connection"></a>SIEM 에이전트 연결

Cloud App Security에서 SIEM에 연결할 수 있게 하려면 다음 IP 주소에 대한 **443 아웃바운드 포트**를 방화벽의 허용 목록에 추가합니다.  


> [!div class="mx-tableFixed"]
> 
> |데이터 센터|IP 주소|  
> |----|----|
> |US1|13.91.91.243|
> |US2|52.184.165.82|
> |US3|40.90.218.198<br>40.90.218.196|
> |EU1|52.174.56.180|
> |EU2|40.81.156.154<br>40.81.156.156|

> [!NOTE]
> Http 연결을 허용 해야 하는 Cloud App Security SIEM 에이전트를 설정 하는 경우 프록시를 지정 하지 않은 경우 http://ocsp.msocsp.com/ 및 포트 80에서 ocsp.digicert.com 합니다. 이는 Cloud App Security 포털에 연결할 때 인증서 해지 상태를 확인하는 데 사용됩니다.

## <a name="app-connector"></a>앱 커넥터

Cloud App Security에서 액세스하는 일부 타사 앱인 경우 이러한 IP 주소를 사용할 수 있습니다. IP 주소를 통해 Cloud App Security에서 로그를 수집하고 Cloud App Security 콘솔에 대한 액세스를 제공할 수 있습니다. 

> [!NOTE]
>Cloud App Security가 이러한 IP 주소에서 거버넌스 작업 및 검사를 수행하기 때문에 공급업체의 활동 로그에 이러한 IP 주소가 표시될 수 있습니다. 

타사 앱에 연결하려면 Cloud App Security가 다음 IP 주소에서 연결할 수 있도록 설정합니다.


> [!div class="mx-tableFixed"]
> 
> |데이터 센터|IP 주소|  
> |----|----|
> |US1|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
> |US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
> |US3|40.90.218.197<br>40.90.218.203|
> |EU1|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|
> |EU2|40.81.156.155<br>40.81.156.153|


## <a name="third-party-dlp-integration"></a>타사 DLP 통합

Cloud App Security에서 stunnel을 통해 데이터를 ICAP 서버에 전송할 수 있도록 하려면 동적 소스 포트 번호를 통해 이러한 IP 주소로 DMZ 방화벽을 엽니다. 

1. **소스 주소** - 이러한 주소는 API 커넥터 타사 앱에 대해 위에 나열된 허용 목록에 있어야 합니다.
2. **원본 TCP 포트** - 동적
3. **대상 주소** - 외부 ICAP 서버에 연결된 stunnel의 하나 또는 두 개의 IP 주소
4. **대상 TCP 포트** - 네트워크에 정의된 대로

> [!NOTE] 
> -  기본적으로 stunnel 포트 번호는 11344로 설정됩니다. 필요한 경우 다른 포트로 변경할 수 있지만 새 포트 번호를 기록해 두어야 합니다.
> - Cloud App Security가 이러한 IP 주소에서 거버넌스 작업 및 검사를 수행하기 때문에 공급업체의 활동 로그에 이러한 IP 주소가 표시될 수 있습니다. 

타사 앱에 연결하고 외부 DLP 솔루션과 통합하려면 Cloud App Security가 다음 IP 주소에서 연결할 수 있도록 설정합니다.

> [!div class="mx-tableFixed"]
> 
> |데이터 센터|IP 주소|  
> |----|----|
> |US1|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
> |US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
> |US3|40.90.218.197<br>40.90.218.203|
> |EU1|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|
> |EU2|40.81.156.155<br>40.81.156.153|

## <a name="mail-server"></a>메일 서버

기본 템플릿 및 설정에서 알림을 보낼 수 있도록 설정하려면 다음 IP 주소를 스팸 방지 허용 목록에 추가합니다. Cloud App Security 전용 메일 IP 주소: 

- 65.55.234.192/26
- 207.46.200.0/27
- 65.55.52.224/27
- 94.245.112.0/27
- 111.221.26.0/27
- 207.46.50.192/26

이메일 보낸 사람 ID를 사용자 지정하려는 경우 Microsoft Cloud App Security에서 타사 이메일 서비스인 MailChimp®를 사용하여 사용자 지정을 가능하게 합니다. 작동하려면 Microsoft Cloud App Security 포털에서 **설정**으로 이동합니다. **메일 설정**을 선택하고 MailChimp의 서비스 약관 및 개인정보처리방침을 검토합니다. 그런 다음, 사용자를 대신하여 MailChimp를 사용할 수 있는 권한을 Microsoft에 제공합니다.

보낸 사람 ID를 사용자 지정하지 않으면 모든 기본 설정을 사용하여 이메일 알림이 전송됩니다.

MailChimp를 사용하려면 다음 IP 주소를 스팸 방지 허용 목록에 추가하여 알림이 전송될 수 있도록 합니다. 198.2.134.139(mail1.cloudappsecurity.com)


## <a name="log-collector"></a>로그 수집기 

로그 수집기를 사용하여 클라우드 검색 기능을 사용하도록 설정하고 조직에서 섀도 IT를 검색하려면 다음 항목을 엽니다.

- 로그 수집기가 인바운드 FTP 및 Syslog 트래픽을 수신하도록 허용합니다.
- 로그 수집기가 포트 443에서 포털(예: contoso.cloudappsecurity.com)에 대한 아웃바운드 트래픽을 시작하도록 허용합니다.
- 로그 수집기가 443 포트에서 Azure Blob Storage에 대한 아웃바운드 트래픽을 시작하도록 허용합니다.


  | 데이터 센터 |                        URL                        |
  |-------------|---------------------------------------------------|
  |     US1      |   https://adaprodconsole.blob.core.windows.net/   |
  |     US2     | https://prod03use2console1.blob.core.windows.net/ |
  |     US3     |https://prod5usw2console1.blob.core.windows.net/   |
  |     EU1      | https://prod02euwconsole1.blob.core.windows.net/  |
  |     EU2     |https://prod4uksconsole1.blob.core.windows.net/    |

> [!NOTE]
> - 방화벽에 고정 IP 주소 액세스 목록이 필요하고 URL 기반 허용 목록을 지원하지 않는 경우 로그 수집기가 443 포트에서 [Microsoft Azure 데이터 센터 IP 범위](https://www.microsoft.com/download/details.aspx?id=41653)에 대한 아웃바운드 트래픽을 시작하도록 허용합니다.
>- 로그 수집기가 Cloud App Security 포털에 대한 아웃바운드 트래픽을 시작하도록 허용합니다.
>- 로그 수집기를 설정 하는 경우 프록시를 지정 하지 않은 경우 http 연결을 허용 하도록 http://ocsp.msocsp.com/ 및 포트 80에서 ocsp.digicert.com 합니다. 이는 Cloud App Security 포털에 연결할 때 인증서 해지 상태를 확인하는 데 사용됩니다.

## <a name="next-steps"></a>다음 단계
 
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  

