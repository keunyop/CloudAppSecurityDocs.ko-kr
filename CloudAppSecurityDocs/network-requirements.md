---
title: "Cloud App Security 네트워크 요구 사항 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security를 사용하기 위해 열어야 하는 IP 주소와 포트에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a43adb2dfbfce0164384bd9fccb87d602e9eb7b7
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2017
---
# <a name="network-requirements"></a>네트워크 요구 사항

이 항목에서는 Cloud App Security를 사용하기 위해 허용해야 하는 포트 및 IP 주소 목록과 허용 목록을 제공합니다. 

연결된 Cloud App Security 데이터 센터를 확인하는 방법에 대한 자세한 내용은 [API 토큰](api-tokens.md)을 참조하세요.



## <a name="portal-access-siem-agent-authentication-gateway-and-log-collector"></a>포털 액세스, SIEM 에이전트, 인증 게이트웨이 및 로그 수집기

포털 및 인증 게이트웨이에 액세스하고 Cloud App Security가 SIEM에 연결하도록 하고 Cloud App Security 로그 수집기가 실행되도록 하려면 다음 IP 주소에 대한 **아웃바운드 포트 443**을 방화벽의 허용 목록에 추가해야 합니다.  


> [!div class="mx-tableFixed"]
|데이터 센터|IP 주소|  
|----|----|
|US1|13.91.91.243<br></br>52.183.75.62|
|EU1|52.174.56.180<br></br>13.80.125.22|

## <a name="app-connector-access-and-external-dlp-integration"></a>앱 커넥터 액세스 및 외부 DLP 통합

타사 앱에 연결하고 외부 DLP 솔루션과 통합하려면 Cloud App Security가 다음 IP 주소에 연결할 수 있도록 합니다.


> [!div class="mx-tableFixed"]
|데이터 센터|IP 주소|  
|----|----|
|US1|104.209.35.177<br></br>13.91.98.185<br></br>40.118.211.172<br></br>13.93.216.68<br></br>13.91.61.249<br></br>13.93.233.42<br></br>13.64.196.27<br></br>13.64.198.97<br></br>13.64.199.41<br></br>13.64.198.19|
|EU1|13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|


### <a name="app-connector"></a>앱 커넥터
Cloud App Security에서 액세스하는 일부 타사 앱의 경우 Cloud App Security에서 로그를 수집할 수 있게 하고 Cloud App Security 콘솔에 대한 액세스를 제공하는 데 이러한 IP 주소가 사용될 수 있습니다. 

> [!NOTE]
>Cloud App Security가 이러한 IP 주소에서 거버넌스 작업 및 검사를 수행하기 때문에 공급업체의 활동 로그에 이러한 IP 주소가 표시될 수 있습니다. 
  

### <a name="dlp-integration"></a>DLP 통합

Cloud App Security에서 stunnel을 통해 데이터를 ICAP 서버에 전송하려면 동적 소스 포트 번호를 통해 이러한 IP 주소로 DMZ 방화벽을 엽니다. 

1.  소스 주소: 소스 주소는 API 커넥터 타사 앱에 대해 위에 나열된 허용 목록에 있어야 합니다.
2.  원본 TCP 포트: 동적
3.  대상 주소: 외부 ICAP 서버에 연결된 stunnel의 IP 주소 하나 또는 두 개
4.  대상 TCP 포트: 네트워크에 정의된 대로

> [!NOTE] 
> 기본적으로 stunnel 포트 번호는 11344로 설정됩니다. 필요한 경우 다른 포트로 변경할 수 있지만 새 포트 번호를 기록해 두어야 합니다.

## <a name="email-server"></a>메일 서버

Cloud App Security 전용 메일 IP 주소: 

198.2.134.139(mail1.cloudappsecurity.com)

알림을 보낼 수 있도록 스팸 방지 서비스에서 이 IP 주소를 허용 목록에 포함해야 합니다.
    



  
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  

   