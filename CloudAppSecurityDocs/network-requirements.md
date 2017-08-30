---
title: "Cloud App Security 네트워크 요구 사항 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security를 사용하기 위해 열어야 하는 IP 주소와 포트에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dac230e191c7c2d8159a2f373e6ef939fdd841a4
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2017
---
# <a name="network-requirements"></a>네트워크 요구 사항

이 항목에서는 Cloud App Security를 사용하기 위해 허용해야 하는 포트 및 IP 주소 목록과 허용 목록을 제공합니다. 


## <a name="portal-access"></a>포털 액세스

포털 액세스의 경우 Cloud App Security 포털에 액세스할 수 있도록 다음 IP 주소를 방화벽 허용 목록에 추가해야 합니다.  
  
104.42.231.28  


## <a name="app-connector-access"></a>앱 커넥터 액세스

Cloud App Security에서 액세스하는 일부 타사 앱의 경우 Cloud App Security에서 로그를 수집할 수 있게 하고 Cloud App Security 콘솔에 대한 액세스를 제공하기 위해 허용 목록에 다음 IP 주소를 추가해야 할 수 있습니다.  
  
104.209.35.177  
13.91.98.185 40.118.211.172 13.93.216.68 13.91.61.249 13.93.233.42 13.64.196.27 13.64.198.97 13.64.199.41 13.64.198.19

> [!NOTE]
>Cloud App Security가 이러한 IP 주소에서 거버넌스 작업 및 검사를 수행하기 때문에 공급업체의 활동 로그에 이러한 IP 주소가 표시될 수 있습니다. 
  

## <a name="siem-agent-and-log-collector"></a>SIEM 에이전트 및 로그 수집기

Cloud App Security를 SIEM에 연결하고 Cloud App Security 로그 수집기를 실행하려면 다음을 열어야 합니다.

- 104.42.231.28에 아웃바운드 포트 443

## <a name="external-dlp-integration"></a>외부 DLP 통합

Cloud App Security에서 stunnel을 통해 데이터를 ICAP 서버에 전송하려면 동적 소스 포트 번호를 통해 Cloud App Security에서 사용되는 외부 IP 주소로 DMZ 방화벽을 엽니다. 

1.  소스 주소: 이러한 소스 주소는 API 커넥터 타사 앱에 대해 위에 나열된 허용 목록에 있어야 합니다.
2.  원본 TCP 포트: 동적
3.  대상 주소: 외부 ICAP 서버에 연결된 stunnel의 IP 주소 하나 또는 두 개
4.  대상 TCP 포트: 네트워크에 정의된 대로

> [!NOTE] 
> 기본적으로 stunnel 포트 번호는 11344로 설정됩니다. 필요한 경우 다른 포트로 변경할 수 있지만 새 포트 번호를 기록해 두어야 합니다.



  
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  

   