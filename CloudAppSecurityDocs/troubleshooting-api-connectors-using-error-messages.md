---
title: 앱 커넥터 오류 메시지 문제 해결 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 API 앱 커넥터 오류 메시지 목록과 각각에 대한 권장 해결 방법을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4b6ac04a-4653-4c4a-bd6f-5926743475cc
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: acdb5bee55a296af2886c39010ce524a39de5f2d
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568503"
---
# <a name="troubleshooting-app-connectors-using-error-messages"></a>오류 메시지를 사용하여 앱 커넥터 문제 해결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 API 앱 커넥터 오류 메시지 목록과 각 오류에 대한 권장 해결 방법을 제공합니다.

## <a name="troubleshooting"></a>문제 해결

API 앱 커넥터를 사용하여 클라우드 앱에 연결하려고 할 때 앱 커넥터 대화 상자에 앱 커넥터 오류가 표시될 수 있습니다.


> [!div class="mx-tableFixed"]
> 
> |오류 메시지|관련 앱|Description|해결 방법|
> |----|----|----|------------|
> |HttpRequestFailure: 서버에서 반환함: 400 잘못된 요청: {"error":{"code":"AF20012","message":"지정된 테넌트 ID(Tenant_ID 위치)가 시스템에서 잘못 구성되었습니다."|Office 365 |할당된 Office 365 라이선스가 없습니다. |테넌트에 하나 이상의 Office 365 라이선스를 할당하세요.| 
> |AuthFatalFailureException: com.box.boxjavalibv2.exceptions.BoxServerException: {"error":"invalid_grant","error_description":"잘못된 새로 고침 토큰"}|상자|Box 새로 고침 토큰이 잘못되었습니다.|프로세스에 따라 Box를 Cloud App Security에 다시 연결하세요.|
> |BoxRestException: 응답을 구문 분석하지 못했습니다.|상자|내부 오류|지금 테스트 링크를 다시 클릭하여 Box에 대한 연결을 테스트하세요.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"잘못된 새로 고침 토큰"}'|상자|Box 새로 고침 토큰이 잘못되었습니다.|프로세스에 따라 Box를 Cloud App Security에 다시 연결하세요.|
> |BoxServerException: 엔터프라이즈 계정이 없으면 사용자가 이 기능에 액세스할 수 없습니다.|상자|Box 계정이 엔터프라이즈 계정이 아닙니다.|Box 라이선스를 Enterprise 버전의 Box로 업그레이드한 다음 프로세스에 따라 Box를 Cloud App Security에 다시 연결하세요.|
> |BoxServerException: 권한 없음 - 이 서비스를 인증할 수 없습니다.|상자|Box 관리자가 Box에서 Cloud App Security 애플리케이션을 삭제했습니다.|프로세스에 따라 Box를 Cloud App Security에 다시 연결하세요.|
> |HttpRequestFailure: 서버에서 반환함: 401 권한 없음|Okta|Okta 토큰이 잘못되었습니다.|프로세스에 따라 Okta를 Cloud App Security에 다시 연결하세요.|
> |IOException:|Okta|내부 오류|기술 지원 서비스에 문의하십시오.|
> |HttpRequestFailure: 서버에서 반환함: 404 찾을 수 없음|Okta|내부 오류|기술 지원 서비스에 문의하십시오.|
> |SocketTimeoutException: 읽기 시간 초과|Salesforce|내부 오류|지금 테스트 링크를 다시 클릭하여 Salesforce에 대한 연결을 테스트하세요.|
> |HttpRequestFailure: 서버에서 반환함: 400 잘못된 요청|Salesforce|Salesforce에 대한 연결이 완료되지 않았거나 만료되었습니다.|프로세스에 따라 Salesforce를 Cloud App Security에 다시 연결하세요.|
> |HttpRequestFailure: 서버에서 반환함: 401 권한 없음|Office 365|내부 문제|지금 테스트 링크를 다시 클릭하세요.|
> |TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: 자격 증명 유효성 검사 오류 AADSTS70008: 제공된 인증 코드 또는 새로 고침 토큰이 만료되었습니다. 이 사용자 및 리소스에 대해 새로운 대화형 권한 부여 요청을 보냅니다.|Office 365|토큰이 만료됨|프로세스에 따라 Office 365를 Cloud App Security에 다시 연결하세요.|
> |SocketTimeoutException: 읽기 시간 초과|Office 365|내부 오류|지금 테스트 링크를 다시 클릭하세요.|
> |NullPointerException|Office 365|내부 오류|기술 지원 서비스에 문의하십시오.|
> |IgniteException|Office 365|도메인 또는 사용자가 잘못되었습니다.|설정을 다시 설정하고 프로세스에 따라 Office 365를 Cloud App Security에 다시 연결합니다.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: 자격 증명 유효성 검사 오류 AADSTS70008: 제공된 인증 코드 또는 새로 고침 토큰이 만료되었습니다. 이 사용자 및 리소스에 대해 새로운 대화형 권한 부여 요청을 보냅니다.|Office 365|도메인 또는 사용자가 잘못되었습니다.|설정을 다시 설정하고 프로세스에 따라 Office 365를 Cloud App Security에 다시 연결합니다.|
> |HttpRequestFailure: 서버에서 반환함: 400 잘못된 요청|Office 365|내부 오류|몇 분 후에 지금 테스트 링크를 다시 클릭하세요. 그래도 작동하지 않으면 프로세스에 따라 Office 365를 Cloud App Security에 다시 연결하세요.|
> |GoogleJsonResponseException: 401 권한 없음|G Suite|액세스가 거부되었습니다. 활동 레코드를 읽을 수 있는 권한이 없습니다. G Suite에 로그인한 사용자는 관리 사용자여야 합니다.|프로세스에 따라 관리자 계정을 사용하여 G Suite를 Cloud App Security에 다시 연결하세요.|
> |GoogleJsonResponseException: 403 사용할 수 없음|G Suite|G Suite API를 실행하는 동안 문제가 발생했습니다.|G Suite용 Cloud App Security 앱 커넥터를 방금 배포한 경우 다음 사항을 확인합니다. Unlimited를 클릭한 경우 G Suite 계정이 실제로 무제한인지 확인합니다. 그렇지 않으면 앱 커넥터를 다시 실행하고 무제한 계정에 대한 옵션을 선택 취소하세요. 설정하는 동안 정의한 범위가 올바른지 확인하세요. 새 배포가 아닌 경우 이 오류가 표시되면 오늘의 API 제한에 도달하여 G Suite 이벤트가 내일 갱신될 수 있습니다.|
> |TokenResponseException: 400 잘못된 요청|G Suite|G Suite에 대한 연결이 완료되지 않았거나 만료되었습니다.|프로세스에 따라 G Suite를 Cloud App Security에 다시 연결하세요.|
> |RuntimeException: com.adallom.adalib.httputils.exceptions.HttpRequestFailure: 서버에서 반환함: 403 사용할 수 없음|ServiceNow|사용 권한이 올바르지 않습니다.|프로세스에 따라 관리자 계정을 사용하여 ServiceNow를 Cloud App Security에 다시 연결하세요.|
> |HttpRequestFailure: 서버에서 반환함: 401 권한 없음|Exchange Online|사용자 또는 암호가 올바르지 않습니다.|사용자 이름 및 암호가 올바른지 확인하고 프로세스에 따라 Exchange Online을 Cloud App Security에 다시 연결하세요.|
> |HttpRequestFailure: 서버에서 반환함: 404 찾을 수 없음|Exchange Online|Exchange Online에 로그인하는 데 사용하는 사용자에게 Exchange Online의 기본 사서함이 없습니다(예: Azure AD에 존재하지 않는 사용자 또는 Azure AD에 존재하지만 Exchange Online 라이선스가 없는 사용자).|프로세스에 따라 새 관리자 계정을 사용하여 Exchange Online을 Cloud App Security에 다시 연결하세요.|
> |NullPointerException|AWS|내부 오류|기술 지원 서비스에 문의하십시오.|
> |HttpRequestFailure: 서버에서 반환함: 500 내부 서버 오류|모든 앱|앱에서 오류가 발생했습니다.|앱의 상태를 확인하세요.|
> |서비스 시간 초과|모든 앱|Cloud App Security와 앱 간의 연결에서 시간 초과가 검색되었습니다. 이 오류는 앱의 문제 때문일 수 있습니다.|나중에 다시 시도하십시오.|

## <a name="next-steps"></a>다음 단계

[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  

