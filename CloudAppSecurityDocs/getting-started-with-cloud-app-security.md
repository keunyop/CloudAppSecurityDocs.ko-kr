---
title: "Cloud App Security 시작 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security 시작 및 실행에 대한 프로세스를 간략하게 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 8b454edde557c408b644c9bff6f7bf6136ba9819


---

# <a name="getting-started-with-cloud-app-security"></a>Cloud App Security 시작
Cloud App Security는 고객이 향상된 활동 가시성 및 중요한 회사 데이터의 보호 강화를 통해 제어를 유지하는 동시에 클라우드 응용 프로그램의 혜택을 이용할 수 있도록 도와줍니다.  이 설명서에서는 Cloud App Security에서 작업하는 다음 단계를 안내합니다.  
  
조직에서 제품을 사용하려면 Cloud App Security에 대한 라이선스가 있어야 합니다. 자세한 내용은 [Cloud App Security를 구입하는 방법](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx) 및 [라이선싱 리소스](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx)를 참조하세요.  
  
>[!NOTE]
>Cloud App Security에는 Office 365 라이선스가 필요하지 않습니다.  
  
## <a name="get-started-quickly-with-cloud-app-security"></a>빠르게 Cloud App Security 시작  
  
|수행할 작업:|작업|필수 여부|방법:|설명|  
|-------------------------|----------|---------------|-------------|-----------------|  
|1단계. [클라우드 검색 설정](set-up-cloud-discovery.md).|트래픽 로그 업로드|필수|**연속 Cloud Discovery 보고서 만들기**<br /><br /> 1.   **설정** -> **Cloud Discovery 설정**으로 이동합니다.<br /><br /> 2.    **자동으로 로그 업로드**를 클릭합니다.<br /><br /> 3.   **데이터 원본** 탭에서 데이터 원본을 추가합니다.<br /><br /> 4.    **로그 수집기** 탭에서 로그 수집기를 구성합니다.<br /><br /> Cloud Discovery 스냅숏 보고서 만들기<br /><br /> 1.    **검색** -> **새 스냅숏 보고서 만들기**로 이동하고 단계를 따릅니다.|**Cloud Discovery 보고서를 구성해야 하는 이유는 무엇일까요?** 조직의 Shadow IT를 파악하는 것이 중요합니다.  <br />로그를 분석한 후에는 누가 어떤 장치에서 어떤 클라우드 앱을 사용하는지 쉽게 검색할 수 있습니다.|  
|2단계. [앱에 대해 인스턴트 표시 유형, 보호 및 거버넌스 작업 사용](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).|앱 연결|필수|1.   **설정** -> **사용 권한 앱**으로 이동합니다.<br /><br /> 2. **앱 연결**을 클릭하고 앱을 선택합니다.<br /><br /> 3. 구성 단계에 따라 앱을 연결합니다.|**앱을 연결해야 하는 이유는 무엇일까요?**<br /><br /> 앱을 연결한 후에만 보다 심층 분석을 통해 클라우드 앱에 대한 클라우드 환경의 활동, 파일 및 계정을 조사할 수 있습니다.|  
|3단계. [정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md).|정책 만들기|필수|**정책 만들기**<br /><br /> 1.  **제어** -> **템플릿**으로 이동합니다.<br /><br /> 2.    목록에서 정책 템플릿을 선택하고 (+) **정책 만들기**를 클릭합니다.<br /><br /> 3.  요구에 맞게 정책을 사용자 지정하고(필터, 동작 및 기타 구성 선택) **만들기**를 클릭합니다.<br /><br /> 4.    **정책** 탭에서 직접 만든 정책을 클릭하여 관련된 일치 항목(활동, 파일, 경고 등)을 확인합니다.<br /><br /> 팁 - 각 **위험 범주**에 대한 정책을 만들어 모든 클라우드 환경 보안 시나리오에 적용합니다.|**정책은 조직에 어떤 도움을 줄 수 있을까요?**<br /><br /> 정책은 추세를 모니터링하고, 보안 위협을 확인하고, 사용자 지정 보고서 및 경고를 생성하는 도구를 제공합니다. 정책을 사용하여 다양한 거버넌스 작업, DLP 및 파일 공유 컨트롤을 만들 수 있습니다.|  
|4단계. [환경 개인 설정](general-setup.md#Adallom_mailsettings).|조직 정보 추가|권장|**메일 설정 입력**<br /><br /> 1. **설정** -> **메일 설정**으로 이동합니다.<br /><br /> 2.   **메일 보낸 사람 ID**에서 메일 주소와 표시 이름을 입력합니다.<br /><br /> 3. **메일 디자인**에서 조직의 메일 템플릿을 업로드합니다.<br /><br /> **관리자 알림 설정**<br /><br /> 1.    탐색 모음에서 사용자 이름을 클릭하고 **사용자 설정**으로 이동합니다.<br /><br /> 2.    **알림**에서 시스템 알림에 대해 설정할 방법을 구성합니다.<br /><br /> 3.  **Save**을 클릭합니다.<br /><br /> **점수 메트릭 사용자 지정**<br /><br /> 1.  **설정** -> **Cloud Discovery 설정**으로 이동합니다.<br /><br /> 2.    **점수 메트릭 구성**에서 다양한 위험 값의 중요도를 구성합니다.<br /><br /> 3.    **Save**을 클릭합니다.<br /><br /> 이제 검색된 앱에 제공되는 위험 점수가 조직 요구 및 우선 순위에 따라 정확하게 구성됩니다.|**사용자 환경을 개인 설정해야 하는 이유는 무엇일까요?**<br /><br /> 일부 기능은 사용자의 요구에 맞게 사용자 지정한 경우에 가장 잘 작동합니다.  <br />고유한 메일 템플릿을 사용하여 사용자에게 더 나은 환경을 제공하고, 수신할 알림을 결정하고, 위험 점수 메트릭을 조직의 기본 설정에 맞게 사용자 지정합니다.|  
|5단계. [필요에 따라 데이터 구성](general-setup.md#IPtagsandRanges).|중요한 설정 구성|권장|**IP 주소 태그 만들기**<br /><br /> 1.   **설정** -> **IP 주소 태그**로 이동합니다.<br /><br /> 2. (+) **IP 주소 범위 추가**를 클릭합니다.<br /><br /> 3.    IP 범위 **세부 정보**, **위치**, **태그** 및 **범주**를 입력합니다.<br /><br /> 4. **만들기**를 클릭합니다.<br /><br /> 이제 정책을 만들 때, 필터링할 때 및 데이터 뷰를 만들 때 IP 태그를 사용할 수 있습니다.<br /><br /> **뷰 만들기**<br /><br /> 1.  **설정** -> **Cloud Discovery 설정**으로 이동합니다.<br /><br /> 2.    **데이터 뷰**에서 (+) **데이터 뷰 추가**를 클릭합니다.<br /><br /> 3.  구성 단계를 따릅니다.<br /><br /> 4.  **만들기**를 클릭합니다.<br /><br /> 이제 사업부 또는 IP 범위와 같은 사용자 기본 설정에 따라 검색된 데이터를 볼 수 있습니다.<br /><br /> **도메인 추가**<br /><br /> 1.    **설정** -> **일반 설정**으로 이동합니다.<br /><br /> 2.    **조직 세부 정보**에서 조직의 내부 도메인을 추가합니다.<br /><br /> 3. **Save**을 클릭합니다.|**이러한 설정을 구성해야 하는 이유는 무엇일까요?**<br /><br /> 이러한 설정은 콘솔에서 다양한 기능을 더 쉽고 잘 제어할 수 있게 합니다. IP 태그를 사용하면 더 쉽게 요구에 맞는 정책을 만들고 정확하게 데이터를 필터링할 수 있습니다. 데이터 뷰를 사용하여 데이터를 논리적 범주로 그룹화할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
[일반 설정](general-setup.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


