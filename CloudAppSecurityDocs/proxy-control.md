---
title: "Cloud App Security 프록시를 사용하여 정책을 만들고 클라우드 앱 사용 제어 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security를 사용하여 정책을 만들고 클라우드 앱 사용을 제어하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/16/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b419aff0-3f50-4917-9ee2-9ecf7539a5d7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4544f5b48484f9341bb85d09d8fdc8d11fd4ba00
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="controlling-app-use-with-proxy-control"></a>프록시 제어를 사용하여 앱 사용 제어

프록시를 배포한 후 원하지 않는 액세스 및 동작을 차단하는 정책을 만들어 조직의 액세스 및 세션을 제어할 수 있습니다.

## <a name="create-access-control-policies-in-cloud-app-security"></a>Cloud App Security에서 액세스 제어 정책 만들기

액세스 제어 정책을 만들려면:

1.  **제어** 아래에서 **정책**을 선택합니다.

2.  **정책 만들기** 아래에서 **프록시 정책**을 선택한 다음 **활동 유형**으로 **Single Sign-On 로그온**을 선택합니다.

3.  그런 다음 관련 앱 및 필터를 선택하고 원하는 완화 옵션을 선택합니다.

>[!NOTE]
> 필터에서 **장치 태그**를 선택하고 **관리되는 장치**와 같거나 같지 않도록 설정할 수 있습니다. [관리되는 장치](#_Managed_devices)에 대한 자세한 내용은 아래를 참조하세요.

또한, **작업 완화**에서 **로그** 또는 **액세스 차단**을 선택하거나 **Cloud App Security 경로**를 선택할 수 있습니다. 그러면 세션에서 정책을 모니터링하고 만들 수 있습니다. 이 부분은 [Cloud App Security에서 세션 제어 정책 만들기](#_Creating_session_control)에 자세히 설명되어 있습니다.

## <a name="create-session-control-policies-in-cloud-app-security"></a>Cloud App Security에서 세션 제어 정책 만들기 

프록시를 배포한 후 Cloud App Security 포털에서 세션 정책을 정의하여 세션 제어 기능을 추가할 수 있습니다.

조직 전체에 배포하기 전에 먼저 작은 사용자 그룹에서 세션 제어를 사용할 수 있도록 설정하여 시작하는 것이 좋습니다. 또한, 모든 세션 또는 대부분의 세션에 세션 제어를 사용하지 않는 것이 좋습니다. 세션 제어는 제한 사항이 있는 에이전트 없는 배포를 기반으로 하기 때문에 장치와 앱에 대한 제어가 제한되어 있거나 아예 없는 경우도 처리하도록 설계되어 있습니다.

세션 제어 정책을 만들려면:

1.  [액세스 정책](#working-with-proxy-control-features)을 만든 다음 완화 작업으로 **Cloud App Security 경로**를 선택합니다.

2.  **제어** 아래에서 **정책**으로 이동하고 **정책 만들기** 아래에서 **프록시 정책**을 선택합니다.

3.  그런 다음 **활동 유형**으로 **파일 다운로드** 또는 **보고서 내보내기**를 선택합니다. 관련 앱 및 필터를 선택하고 필요에 따라 완화 옵션을 선택합니다.

## <a name="enabling-managedunmanaged-device-control"></a>관리되는/관리되지 않는 장치 제어 사용

### <a name="step-1-deploy-certificates"></a>1단계: 인증서 배포

클라우드에 연결 중인 장치 중에서 관리되는 장치와 관리되지 않는 장치를 Cloud App Security에서 식별하도록 하려면 클라이언트 인증서를 배포해야 합니다. 이는 다양한 방법으로 수행 가능한데, 보통 기존 모바일 장치 관리 솔루션의 인증서를 활용하거나 Active Directory 그룹 정책을 사용함으로써 수행할 수 있습니다.

### <a name="step-2-upload-the-root-certificate-to-cloud-app-security"></a>2단계: Cloud App Security에 루트 인증서 업로드

Cloud App Security 포털에서 관리되는 장치의 식별을 사용하려면 먼저 인증 기관 루트 인증서를 업로드해야 합니다.

1.  [설정] 코그를 클릭하고 **관리되는 장치**를 선택합니다.

2.  **장치 식별**을 사용하도록 설정합니다.

3. 루트 인증서를 업로드합니다.

![클라우드 앱 보안 프록시 관리되는 장치 인증서](./media/managed-device-cert.png)

### <a name="step-3-create-managed-device-policies"></a>3단계: 관리되는 장치 정책 만들기

루트 인증서를 업로드한 후 **관리되는 장치**와 같거나 같지 않은 **장치 태그** 필터를 사용하여 프록시 정책을 만들거나 활동 로그에서 이벤트를 검색합니다.

관리되는 장치를 식별하기 위하여 클라이언트 인증서를 사용하는 경우 세션을 차단하거나 모니터링하기 전에 먼저 모니터링 모드에서 시작하는 것이 좋습니다. 즉, 완화 작업이 **로그만**인 **관리되는 장치** 필터를 사용하여 액세스 정책을 정의하라는 뜻입니다. 사용자에 대한 경험을 어느 정도 쌓은 후에는 액세스 차단 또는 세션 모니터링 등의 다른 완화 작업을 추가할 수 있습니다.


## <a name="see-also"></a>참고 항목  
[Cloud App Security 프록시 작업](proxy-intro.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  