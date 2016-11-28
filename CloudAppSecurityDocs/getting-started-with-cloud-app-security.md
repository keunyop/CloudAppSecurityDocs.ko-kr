---
title: "Cloud App Security 시작 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security 시작 및 실행에 대한 프로세스를 간략하게 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/21/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3c342e019dfca316ee89f68de60886d848abdb17
ms.openlocfilehash: 7137b7f362718f36a416d3c8e33040d208a92126


---

# <a name="getting-started-with-cloud-app-security"></a>Cloud App Security 시작
Cloud App Security는 클라우드 응용 프로그램의 이점을 활용하도록 도우면서도 회사 리소스의 제어를 유지할 수 있습니다. 클라우드 활동의 가시성을 개선하고 회사 데이터의 보호를 강화할 수 있도록 돕는 방식으로 작동합니다. 이 항목에서는 Cloud App Security을 설정하고 사용하는 단계를 안내합니다.  

조직에 Cloud App Security 사용 라이선스가 있어야 합니다. 자세한 내용은 [Cloud App Security를 구입하는 방법](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)의 라이선싱 리소스를 참조하세요.  

>[!NOTE]
>Office 365 라이선스가 없어도 Cloud App Security를 사용할 수 있습니다.  

## <a name="get-started-quickly-with-cloud-app-security"></a>빠르게 Cloud App Security 시작  

|수행할 작업|작업|필수 여부|방법|설명|  
|-------------------------|----------|---------------|-------------|-----------------|  
|1단계. [클라우드 검색 설정](set-up-cloud-discovery.md).|트래픽 로그 업로드|필수|**연속 Cloud Discovery 보고서를 만들려면**<br /><br /> 1. **설정** > **Cloud Discovery 설정**으로 이동합니다.<br /><br /> 2. **자동으로 로그 업로드**를 선택합니다.<br /><br /> 3. **데이터 원본** 탭에서 원본을 추가합니다.<br /><br /> 4. **로그 수집기** 탭에서 로그 수집기를 구성합니다.<br /><br /> **Cloud Discovery 스냅숏 보고서를 만들려면**<br /><br /> 1. **검색** > **새 스냅숏 보고서 만들기**로 이동하고 표시되는 단계를 따릅니다.|**Cloud Discovery 보고서를 구성해야 하는 이유는 무엇일까요?**<br /> 조직의 섀도 IT를 파악하는 것이 중요합니다. <br />로그를 분석한 후에는 누가 어떤 장치에서 어떤 클라우드 앱을 사용하는지 쉽게 검색할 수 있습니다.|
|2단계. [응용 프로그램에 대해 인스턴트 표시 유형, 보호 및 거버넌스 작업을 사용합니다](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).|앱 연결|필수|1. **설정** > **앱 커넥터**로 이동합니다.<br /><br /> 2. **응용 프로그램 연결**을 선택하고 응용 프로그램을 선택합니다.<br /><br /> 3. 구성 단계에 따라 앱을 연결합니다.|**앱을 연결해야 하는 이유는 무엇일까요?**<br />응용 프로그램을 연결한 후, 클라우드 환경에서 응용 프로그램의 활동, 파일 및 계정을 조사할 수 있도록 심층 정보를 확인할 수 있습니다.|
|3단계. [정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md).|정책 만들기|필수|**정책을 만들려면**<br /><br /> 1. **제어** > **템플릿**으로 이동합니다.<br /><br /> 2. 목록에서 정책 템플릿을 선택하고 (+) **정책 만들기**를 선택합니다.<br /><br /> 3. 정책을 사용자 지정한 다음(필터, 작업 및 기타 설정 선택) **만들기**를 선택합니다.<br /><br /> 4. **정책** 탭에서 정책을 선택하여 관련된 일치 항목(활동, 파일, 경고)을 확인합니다.<br /><br /> 팁: 모든 클라우드 환경 보안 시나리오에 적용하려면 각 **위험 범주**별로 정책을 만듭니다.|**정책은 조직에 어떤 도움을 줄 수 있을까요?**<br />정책을 사용하면 추세 모니터링, 보안 위협 파악, 사용자 지정 보고서 및 경고 생성에 도움이 됩니다. 정책을 사용하면 거버넌스 작업을 만들고 데이터 손실 방지 및 파일 공유 컨트롤을 설정할 수 있습니다.|
|4단계. [환경 개인 설정](general-setup.md#Adallom_mailsettings).|조직 정보 추가|권장|**메일 설정을 입력하려면**<br /><br /> 1. **설정** > **메일 설정**으로 이동합니다.<br /><br /> 2. **메일 보낸 사람 ID**에서 메일 주소와 표시 이름을 입력합니다.<br /><br /> 3. **메일 디자인**에서 조직의 메일 템플릿을 업로드합니다.<br /><br /> **관리자 알림을 설정하려면**<br /><br /> 1. 탐색 모음에서 사용자 이름을 선택한 다음 **사용자 설정**으로 이동합니다.<br /><br /> 2. **알림**에서 시스템 알림에 대해 설정할 방법을 구성합니다.<br /><br /> 3. **저장**을 선택합니다.<br /><br /> **점수 메트릭을 사용자 지정하려면**<br /><br /> 1. **설정** > **Cloud Discovery 설정**으로 이동합니다.<br /><br /> 2. **점수 메트릭 구성**에서 다양한 위험 값의 중요도를 구성합니다.<br /><br /> 3. **저장**을 선택합니다.<br /><br /> 이제 검색된 앱에 제공되는 위험 점수가 조직 요구 및 우선 순위에 따라 정확하게 구성됩니다.|**사용자 환경을 개인 설정해야 하는 이유는 무엇일까요?**<br />일부 기능은 사용자의 요구에 맞게 사용자 지정한 경우에 가장 잘 작동합니다. <br />고유한 메일 템플릿을 사용하여 사용자에게 더 나은 환경을 제공하고, 수신할 알림을 결정하고, 위험 점수 메트릭을 조직의 기본 설정에 맞게 사용자 지정합니다.|
|5단계. [필요에 따라 데이터 구성](general-setup.md#IPtagsandRanges).|중요한 설정 구성|권장|**IP 주소 태그를 만들려면**<br /><br /> 1. **설정** > **IP 주소 태그**로 이동합니다.<br /><br /> 2. (+) **IP 주소 범위 추가**를 선택합니다.<br /><br /> 3. IP 범위 **세부 정보**, **위치**, **태그** 및 **범주**를 입력합니다.<br /><br /> 4. **만들기**를 선택합니다.<br /><br /> 이제 정책을 만들 때와 데이터 보기를 필터링하고 만들 때 IP 태그를 사용할 수 있습니다.<br /><br /> **보기를 만들려면**<br /><br /> 1. **설정** > **Cloud Discovery 설정**으로 이동합니다.<br /><br /> 2. **데이터 보기**에서 (+) **데이터 보기 추가**를 선택합니다.<br /><br /> 3. 구성 단계를 따릅니다.<br /><br /> 4. **만들기**를 선택합니다.<br /><br /> 이제 사업부 또는 IP 범위와 같은 사용자 기본 설정에 따라 검색된 데이터를 볼 수 있습니다.<br /><br /> **도메인을 추가하려면**<br /><br /> 1. **설정** > **일반 설정**으로 이동합니다.<br /><br /> 2. **조직 세부 정보**에서 조직의 내부 도메인을 추가합니다.<br /><br /> 3. **저장**을 선택합니다.|**이러한 설정을 구성해야 하는 이유는 무엇일까요?**<br />이러한 설정은 콘솔의 기능을 보다 효율적으로 제어하는 데 도움이 됩니다. IP 태그를 사용하면 더 쉽게 요구에 맞는 정책을 만들고 정확하게 데이터를 필터링할 수 있습니다. 데이터 뷰를 사용하여 데이터를 논리적 범주로 그룹화할 수 있습니다.|  

## <a name="see-also"></a>참고 항목

[Cloud App Security 시작](getting-started-with-cloud-app-security.md)에서 기본적인 사항을 읽으세요.    
기술 지원을 받으려면 [Cloud App Security 보조 지원](http://support.microsoft.com/oas/default.aspx?prid=16031) 페이지를 방문하세요.   
프리미어 고객은 [프리미어 포털](https://premier.microsoft.com/)에서 직접 Cloud App Security를 선택할 수도 있습니다.   



<!--HONumber=Nov16_HO4-->


