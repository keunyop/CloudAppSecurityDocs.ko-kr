---
title: "앱을 연결하여 Cloud App Security의 표시 유형 및 제어 향상 | Microsoft 문서"
description: "이 항목에서는 조직의 클라우드에서 앱에 대해 API 커넥터를 사용하여 앱에 연결하는 프로세스에 대해 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/3/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7e718d77-aae7-4a3a-8421-5ba7cee7d67c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8c9b63f4265876fc1de6a24c6576f917f9d2278
ms.sourcegitcommit: a0290ac2a662994f7771975ef6c20d0b47e9edd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2017
---
Cloud App Security에는 다음과 같이 네트워크에 연결하기 위한 액세스 권한이 필요합니다. 

## <a name="cloud-app-security-system-ip-addresses"></a>Cloud App Security 시스템 IP 주소

다음 IP 주소는 Cloud App Security에서 고객 환경에 연결하는 데 사용됩니다. [ICAP](icap-stunnel.md)를 사용하여 연결할 경우와 앱 커넥터를 연결할 경우 이 주소가 필요합니다. 일부 앱의 경우 Cloud App Security에서 로그를 수집할 수 있게 하고 Cloud App Security 콘솔에 대한 액세스를 제공하기 위해 허용 목록에 다음 IP 주소를 추가해야 할 수 있습니다. 일부 앱에서 이러한 IP 주소를 사용하여 서비스 감사 로그 등에서 Cloud App Security 활동을 식별할 수도 있습니다. 
  
-   로그:  
  
    104.209.35.177  
  
    13.91.98.185
 
    40.118.211.172

    13.93.216.68

    13.91.61.249

    13.93.233.42

    13.64.196.27

    13.64.198.97

    13.64.199.41

    13.64.198.19
  
  
## <a name="cas-portal-url-and-ip-addresses"></a>CAS 포털 URL 및 IP 주소

Cloud App Security URL, 포트 443 및 IP 주소는 CAS API, 로그 수집기 및 SIEM 에이전트에 연결할 때 포털에 대한 고객 액세스, API 연결에 사용됩니다. 
  
     104.42.231.28  

 
  
> [!NOTE]  
>  URL 및 IP 주소가 변경된 경우 업데이트를 가져오려면 [Office 365 URL 및 IP 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)에 설명된 대로 RSS를 구독합니다.  
  

  
## <a name="see-also"></a>참고 항목  
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  

   