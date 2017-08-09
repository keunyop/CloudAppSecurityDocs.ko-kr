---
title: "Cloud App Security 프록시 배포 | Microsoft 문서"
description: "이 항목에서는 Cloud App Security 프록시의 배포 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 75094bde-e135-47fb-b5c6-7e1168919771
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 245e44cdf56b15795f67340442babcb0f688ea9d
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2017
---
# <a name="deploying-the-cloud-app-security-proxy"></a>Cloud App Security 프록시 배포

> [!NOTE]
> 프로덕션 환경에 설치하기 전에 먼저 샌드박스 또는 테스트 환경에서 설치를 시도하는 것이 좋습니다.

아래에 설명된 단계에 따라 Cloud App Security 프록시를 배포하고 액세스 제어와 세션 제어를 사용하도록 설정해야 합니다.

## <a name="prerequisites"></a>필수 구성 요소

-   ID 공급자와 함께 클라우드 앱을 구성하는 작업 환경입니다. 설치 프로세스에는 앱과 ID 공급자의 구성 변경 내용이 포함됩니다.
- ID 공급자와 앱에서 Single Sign-On 설정에 액세스할 수 있는지 확인해야 합니다.

## <a name="deploy-the-proxy"></a>프록시 배포

프로덕션 환경에 프록시를 설치하는 경우 대부분의 사용자가 앱을 사용하지 않는 시간(일반적으로 늦은 밤 또는 주말에)에 설치하는 것이 좋으며, 잠깐 동안의 앱 가동 중지 시간이 발생할 수 있음을 사용자에게 통신으로 알려줍니다.

구성 변경 내용을 적용하기 전에 현재 구성이 정상적으로 작동하는지 확인합니다. 확인 후에는 다음 단계를 수행하세요.

1.  Cloud App Security 포털에서 [설정] 코그로 이동한 다음 **프록시**를 선택합니다.

2. 오른쪽 위에 있는 더하기 기호를 클릭합니다.

3. **프록시에 앱 추가** 창에서 추가할 앱을 선택하고 **시작 마법사**를 클릭합니다. 

 ![Cloud App Security에 앱 추가](./media/proxy-add-app.png)

4. 앱의 Single Sign-On 설정에 있는 Single Sign-On 메타데이터 파일을 업로드합니다. 메타데이터 파일이 없으면 **수동으로 데이터 입력**을 클릭하고 마법사에 따라 요청된 데이터를 제공합니다. 

 ![Cloud App Security 프록시에 Single Sign-On 메타데이터 파일 추가](./media/proxy-w-add-app.png)


5. ID 공급자의 포털에서 다음 단계를 수행합니다. 이는 대부분 ID 공급자 포털의 **응용 프로그램** 아래에서 수행됩니다.

    1. 새 사용자 지정 SAML 앱을 만듭니다. 새 사용자 지정 앱을 만드는 데 필요합니다. 왜냐하면 URL을 변경하고 SAML 특성을 추가해야 하는데 이는 갤러리 앱에서는 가능하지 않기 때문입니다.
    
    2. ID 공급자의 목록에서 기존 앱의 Single Sign-On 구성을 새 사용자 지정 앱에 복사합니다. 사용자 지정 앱의 **식별자**(대상 그룹 또는 엔터티 ID라고도 함)와 실제 앱 Single Sign-On 설정의 **식별자**가 일치하는지 확인해야 합니다. ID 공급자가 두 개의 다른 앱에 같은 **식별자**를 사용하지 못하게 한다면 식별자를 복사한 다음 원래 앱의 식별자를 변경합니다.
    
    3. 현재 원래 앱에 할당된 모든 사용자를 새 사용자 지정 앱에 할당합니다.
    
    ![Cloud App Security 프록시에 Single Sign-On 메타데이터 파일 추가](./media/proxy-w-add-external-config.png)

5. ID 공급자의 Single Sign-On 메타데이터 파일을 업로드합니다. 메타데이터 파일이 없으면 **수동으로 데이터 입력**을 클릭하고 마법사에 따라 요청된 데이터를 제공합니다.  

 ![Cloud App Security 프록시에 Single Sign-On 메타데이터 파일 추가](./media/proxy-w-identity-provider.png)

6. 다음 외부 구성 변경을 ID 공급자의 포털에서, 그 다음에는 새로 만든 사용자 지정 앱에서 수행합니다.

    1. 마법사에서 제공한 URL을 복사합니다. ID 공급자의 포털로 이동해서, 새로 만든 사용자 지정 SAML 앱에 URL을 Single Sign-On URL(또는 회신 URL)로 붙여넣습니다.
    
    2. 프록시 마법사에 제공된 특성과 값을 복사하고 SAML 사용자 지정 특성으로 추가합니다.
    
    3. 앱에서 사용하는 이름 식별자가 전자 메일 주소 형식으로 되어 있는지 확인합니다. 이는 Cloud App Security 프록시가 사용자에게 정책을 적용하도록 만드는 데 필요합니다.
    
    4. 새 사용자 지정 앱의 설정을 저장하고 프록시 마법사에서 **다음**을 클릭합니다.
 ![Cloud App Security 프록시의 ID 공급자 설정 업데이트](./media/proxy-w-ip-external2.png)

4.  그런 다음 앱의 Single Sign-On 설정 페이지에서 다음을 수행합니다.
    1. 현재 앱 설정을 백업합니다.
    
    2. 프록시 마법사의 URL을 SAML Single Sign-On URL에 복사합니다.
    
    3. 앱의 Cloud App Security SAML 인증서를 다운로드합니다.
    
    4. 자신이 만든 사용자 지정 앱에 원래 SAML 인증서가 있던 자리에 이 SAML 인증서를 업로드하고 설정을 저장합니다.
   
    5. 프록시 마법사에서 **마침**을 클릭합니다.


몇 분 안에 앱에 대한 요청의 모든 로그가 Cloud App Security 프록시를 통해 라우팅됩니다. 



### <a name="test-the-configuration"></a>구성 테스트

1.  앱에 로그인해보세요. 로그인에 실패하면 모든 프록시 마법사 단계를 제대로 완료했는지 확인합니다. 

2.  Cloud App Security 포털의 **조사** 아래에서 **활동 로그**를 선택하고 프록시에 의해 캡처된 **Single Sign-On 로그온** 이벤트가 있는지 확인해야 합니다.



## <a name="see-also"></a>참고 항목  
[Cloud App Security 프록시 작업](proxy-intro.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  