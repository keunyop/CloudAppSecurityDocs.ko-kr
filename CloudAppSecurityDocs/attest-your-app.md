---
title: Cloud App Security 앱-증명 | Microsoft Docs
description: 이 문서에서는 Cloud App Security에서 앱을 증명 하기 위한 지침을 제공 합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 29/04/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3536c0a5-fa56-4931-9534-cc7cc4b4dfb0
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: 0799073e7bd82570fd298c1080960170648b7ac1
ms.sourcegitcommit: 9553aed06ebb2378d44bb5685439ae5cba605171
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65048406"
---
# <a name="attest-your-app"></a>증명 하는 앱

Microsoft Cloud App Security 준수 및 보안 세부 정보를 사용 하 여 클라우드 앱 카탈로그에 게 앱의 등급을 최신 상태로 되는지 확인 하는 앱을 증명할 수 있습니다.

앱에 클라우드 앱 카탈로그에 이미 나열 되어 여부는 새 자체 증명 설문지를 제출 합니다. 자체 증명 프로세스에 질문 서 가져오기 세부 정보를 문의 casfeedback@microsoft.com합니다.

설문지를 제출 성공적으로 완료 하려면 아래 설명 하는 서비스 특성을 수행 합니다.

| 필드 | 정보 범주 | 형식 | 사용 가능한 값 | Description |
|------|-------|------|---------|----------|
| 앱 이름 | 일반 | 문자열 | 자유 텍스트 | 이름으로 응용 프로그램에 대 한 클라우드 앱 카탈로그에 표시 됩니다. |
| Description | 일반 | 문자열 | 자유 텍스트 | 에 대 한 짧은 설명 응용 프로그램에 사용자를 하거나 얻을 수 있습니다. |
| 범주| 일반 | 문자열 | 닫기 목록-설문지 제공 | 관련 필드에 따라 앱의 분류입니다. |
| 본사 | 일반 | 국가 코드 | 닫기 목록-설문지 제공 | 공급자의 본사가의 국가입니다.|
| 데이터 센터| 일반 | 국가 코드 배열 * | 닫기 목록-질문 서 (다중 선택)에서 제공 합니다. | 데이터 센터에 상주 하는 국가 (여러 위치 일 수 있음) |
| 호스팅 회사 | 일반 | 문자열 | 자유 텍스트 | 앱에 대 한 서버 호스팅을 제공 하는 회사의 이름입니다. |
| 설립 된 | 일반 | 정수 | YYYY (no 2019 이상) | 공급자가 설립 된 연도입니다. |
| 보유 | 일반 | 문자열 | 개인, 공용 | 공급자가는 공개적으로 비상장 회사 인지 여부를 표시 합니다. |
| 응용 프로그램 도메인 | 일반 | URL 배열 * | 자유 텍스트 | (예를 들어, ' teams.microsoft.com' Microsoft Teams 대 한) 서비스와 상호 작용 하는 데 사용 되는 도메인 목록 |
| 서비스 약관 | 일반 | URL | 자유 텍스트 | 이 앱에 사용자가 동의 해야 앱을 사용 하기 위해 수행 하는 규정 집합을 제공 하나요? |
| 개인 정보 취급 방침 | 일반 | URL | 자유 텍스트 | 법적 구속력이 대 한 링크를 앱의 일부로이 공급자가 고객, 클라이언트 또는 직원 정보를 처리 하는 방법에 관련 된 문서를 수집 합니다. |
| 로그온 URL | 일반 | URL 배열 * | 자유 텍스트 | 사용자가 앱에 로그온 하는 URL입니다. |
| 공급업체 | 일반 | 문자열 | 자유 텍스트 | 이 앱을 제공 하는 공급 업체의 이름입니다. |
| 데이터 형식 | 일반 | 문자열 | 닫기 목록-설문지 제공 | 앱에 사용자는 데이터 형식은 업로드할 수 있습니다?|
| 홈 페이지 | 일반 | URL | 자유 텍스트 | 공급자의 홈 페이지 URL입니다. |
| 최신 위반 | 보안 | Date | MMM-dd-YYYY | 가장 최근의 인시던트는 앱 소유의 중요 한, protected 또는 기밀 데이터를 볼, 도난 또는 개별 사용자가 이렇게 하려면 무단으로 사용 합니다. |
| 미사용 데이터 암호화 방법 | 보안 | 문자열 | 닫기 목록-설문지 제공 | 앱에서 수행 된 미사용 데이터의 암호화 유형입니다. |
| Multi-factor Authentication | 보안 | Boolean | True, False | 이 앱에 multi-factor authentication 솔루션 지원 합니까? |
| IP 주소 제한 | 보안 | Boolean | True, False | 이 앱 앱에서 특정 IP 주소 제한을 지원 합니까? |
| 사용자 감사 내역 | 보안 | Boolean | True, False | 이 앱은 사용자 계정당 감사 내역의 가용성을 지원 합니까? |
| 관리 감사 내역 | 보안 | Boolean | True, False | 이 앱에서 앱 관리 감사 내역의 가용성을 지원 합니까? |
| 데이터 감사 내역 | 보안 | Boolean | True, False | 이 앱은 앱에서 데이터 감사 내역의 가용성을 지원 합니까? |
| 사용자가 데이터를 업로드할 수 있습니다. | 보안 | Boolean | True, False | 이 앱 사용자가 업로드 한 데이터를 지원 하나요? |
| 데이터 분류 | 보안 | Boolean | True, False | 이 앱을는 앱에 업로드 된 데이터 분류에 대 한 옵션을 사용 하도록 설정? |
| 암호 저장 | 보안 | Boolean | True, False | 이 앱을 않습니다를 기억 하 고 앱에서 사용자 암호를 저장 하는 것에 대 한 옵션을 사용 하도록 설정? |
| 사용자 역할 지원 | 보안 | Boolean | True, False | 이 앱은 권한 수준 및 역할에 따른 사용자 배포를 지원 합니까? |
| 파일 공유 | 보안 | Boolean | True, False | 이 앱에 사용자 간의 파일 공유를 허용 하는 기능이 포함 되어 있습니까? |
| 올바른 인증서 이름 | 보안 | Boolean | True, False | 서버를 도메인 이름과 일치 하는 SSL 인증서를 제공 하나요? |
| 신뢰할 수 있는 인증서 | 보안 | Boolean | True, False | 서버를 신뢰할 수 있는 SSL 인증서 (만료 된, 확인 된 없고 신뢰할 수 있는 서명 체인 등)을 제공 하나요? |
| 암호화 프로토콜 | 보안 | 문자열 | 닫기 목록-설문지 제공 | 사용자 끝점과 앱 공급자 간에 지원 되는 전송 계층 보안 (TLS) 암호화 프로토콜의 최신 버전입니다. 서버 인증서의 존재 하지 않거나 유효 하지 않은 경우 암호화 지원 되지 않는 간주 됩니다.|
| Heartbleed 패치 됨 | 보안 | Boolean | True, False | 취약성을 줄이기 위해 Heartbleed 버그에 대 한 패치를 적용 하는 서버의 SSL 구현이 기능 |
| HTTP 보안 헤더: 엄격한 전송 보안 | 보안 | Boolean | True, False | HTTP Strict-전송-보안 웹 사이트에서 앱을 구현한 헤더? |
| HTTP 보안 헤더: Content-Security-Policy | 보안 | Boolean | True, False | HTTP 콘텐츠 보안 정책에서 해당 웹 사이트에서 앱을 구현 하는 헤더? |
| HTTP 보안 헤더: X-프레임-옵션 | 보안 | Boolean | True, False | 옵션-프레임-Http 헤더 사항이 웹 사이트에 앱에서 구현 되었습니까? |
| HTTP 보안 헤더: X-Content-Type-Options | 보안 | Boolean | True, False | Http-콘텐츠-유형-옵션 헤더 사항이 웹 사이트에 앱에서 구현 되었습니까? |
| HTTP 보안 헤더: X-XSS-Protection | 보안 | Boolean | True, False | HTTP X XSS 보호에서 해당 웹 사이트에서 앱을 구현 하는 헤더? |
| SAML 지원 | 보안 | Boolean | True, False | 이 앱 인증 및 권한 부여 데이터를 교환 하기 위한 SAML 표준을 지원 합니까? |
| DROWN 으로부터 보호 | 보안 | Boolean | True, False | 응용 프로그램 서버가 DROWN 공격 으로부터 보호 됩니다? |
| 침투 테스트 | 보안 | Boolean | True, False | 이 앱은 침투 테스트를 검색 하 고 네트워크 취약성 평가 수행? |
| 사용자 인증 필요 | 보안 | Boolean | True, False | 이 앱 인증을 요구 하 고 익명 사용을 허용 하지 않습니다는? |
| 암호 정책: 암호 길이 제한 | 보안 | Boolean | True, False | 이 앱 암호 만들기에 대 한 길이 제한을 적용 합니까? |
| 암호 정책: 문자 조합 | 보안 | Boolean | True, False | 이 앱 암호 생성 시 문자 조합에 적용 합니까? |
| 암호 정책: 암호 기간 변경 | 보안 | Boolean | True, False | 사용자가 자신의 암호를 주기적으로 다시 설정 하려면이 앱에 적용 합니까? |
| 암호 정책: 암호 기록 및 재사용 | 보안 | Boolean | True, False | 이 앱을는 이전 암호의 재사용을 허용 하지 않도록? |
| 암호 정책: 개인 정보 사용 | 보안 | Boolean | True, False | 이 앱 암호의 개인 정보 사용 하지 못하게? |
| 암호 정책 | 보안 | Boolean | True, False | 이 앱에 모범 사례를 준수 하는 암호 정책을 적용 합니까? |
| FINRA | 준수 | Boolean | True, False: 해당 없음 | 이 앱 FINRA를 규제 하 고 투자자 보호의 기능을 적용 하는 의회에서 공인한 비영리 not 조직에 대 한 표준 집합을 준수 하 고 시장 건전성은? |
| FISMA | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 fisma, 정부 정보, 작업 및 위협 으로부터 연방 기관 내의 자산을 보호 하는 종합 프레임 워크를 정의 하는 미국 법규를 준수 합니까? |
| GAAP | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 gaap를 일반적으로 규정 및 표준 재무 보고를 위해 컬렉션인 준수 합니까? |
| HIPAA | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 HIPAA는 개별적으로 식별 가능한 의료 정보의 보안과 기밀성을 보호 하기 위한 표준을 설정 하는 미국 법규를 준수 합니까? |
| ISAE 3402 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 ISAE 3402는 서비스 조직에 적절 한 제어 보증을 제공 하는 글로벌 표준을 사용 하 여 준수 합니까? |
| ISO 27001 | 준수 | Boolean | True, False: 해당 없음 | ISO 27001 인증을 받았습니까 저명한 지침 및 일반 원칙을 시작 하는 회사에 지정 된 인증서를이 앱을 구현, 유지 및 조직 내에서 정보 보안 관리를 개선? |
| ITAR | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 준수, itar 대상 단체를 사용 하 여 내보내기 및 가져오기 물자 및 미국 탄약 목록에 서비스를 제어 하는 규정? |
| SOC 1 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 SOC 1, 서비스 조직에 재무 보고를 통해 내부 제어 사용자 엔터티에서 관련 된 컨트롤에 대 한 보고를 사용 하 여 준수 합니까? |
| SOC 2 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 SOC 2와 하나 이상의 보안, 개인 정보, 가용성, 기밀성 및 처리 무결성에 신뢰 서비스 기준에 따라 비재무 처리에 대 한 보고를 사용 하 여 준수 합니까? |
| SOC 3 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 SOC 3을 자유롭게 배포할 수 있습니다 하 고 선택된 된 기준의 요구 사항에 부합 했다는 경영진의 주장만 포함 하는 신뢰 서비스 기준에 따라 보고를 사용 하 여 준수 합니까? |
| SOX | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 sox를 준수 기업 공시의 정확성을 향상 시킬 수 있을 뿐만 아니라 회계 오류 및 주주와 일반 대 중을 보호 하기 위한 미국 법규? |
| SP 800-53 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 sp80053을 연방 정보 시스템 및 조직을 위한 권장 보안 제어 준수 합니까? |
| SSAE 16 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 서비스 조직의 내부 준수 제어 감사 및 보고 프로세스에 대 한 SSAE 16 표준을 준수 합니까? |
| PCI DSS 버전 | 준수 | 문자열 | 1, 2, 3, 3.1, 3.2, N/A | 이 앱에서 지 원하는 PCI-DSS 프로토콜의 버전입니다. |
| ISO 27018 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 허용 된 제어 및 지침 처리 하 고 공용에서 개인 식별이 가능한 정보 (PII)를 보호 하기 위해 클라우드 컴퓨팅 환경에 일반적으로 설정 하는 iso 27018 준수 합니까? |
| GLBA | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 사용 하 여는 Gramm-Leach-Bliley Act (GLBA), 금융 기관에서 보안과 고객 개인 정보의 비밀을 보호 하기 위한 표준을 수립 해야 하는 준수 합니까? |
| FedRAMP 수준 | 준수 | 문자열 | 높음, 보통, 낮음, 해당 없음 | 이 앱에서 제공 하는 FedRAMP 규격 솔루션의 수준입니다. |
| CSA STAR 수준 | 준수 | 문자열 | 자체 평가, 인증, 증명, C-STAR 평가, 연속 모니터링, 해당 없음 | CSA STAR 프로그램 앱이 인증의 수준 |
| 개인 정보 보호 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 EU 미국 개인 정보 보호 프레임 워크를 유럽인 개인 데이터를 보호 하기 위해 우리 회사에 보다 강력한 의무는 준수 합니까? |
| ISO 27017 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 널리 사용 되는 컨트롤 및 처리 하 고 공용 클라우드 컴퓨팅 환경에서 사용자 정보를 보호 하기 위한 지침을 설정 하는 iso 27017 준수 합니까? |
| COBIT | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 준수 COBIT 거 버 넌 스 및 제어 정보 시스템 및 기술에 대 한 모범 사례를 설정 하 고 정렬 하는 비즈니스 원리를 사용 하 여 IT? |
| COPPA | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 웹 사이트에 13 세 미만 자식 콘텐츠를 제공 하는 온라인 서비스 운영자 요구 사항을 정의 하는 COPPA를 사용 하 여 준수 합니까? |
| FERPA | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 FERPA에 학생 교육 기록의 개인 정보를 보호 하는 연방법에 따라 준수 합니까? |
| GAPP | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 GAPP, 조직에서 개인 정보 위험을 해결 하는 일반적으로 규칙의 컬렉션을 사용 하 여 준수 합니까? |
| HITRUST CSF | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 HITRUST CSF, 정보 보안 규정 및 표준의 요구 사항을 harmonizes 컨트롤 집합을 사용 하 여 준수 합니까? |
| Jericho 포럼 Commandments | 준수 | Boolean | True, False: 해당 없음 | 이 앱 따르지 Jericho 포럼 Commandments, 집합에 대 한 시스템을 설계할 때 사용 되는 원칙 안전한 취소 perimeterized 환경에서 작업 하는 경우? |
| ISO 27002 | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 조직 정보 보안 표준 및 정보 보안 관리 방식에 대 한 일반적인 지침을 설정 하는 iso 27002 준수 합니까? |
| FFIEC | 준수 | Boolean | True, False: 해당 없음 | 이 앱은 인터넷 은행 업무 환경에서 서비스를 인증 하는 데 필요한 위험 관리 제어에 대 한 연방 금융 기관 검사 Council의 지침을 사용 하 여 준수 합니까? |
| 데이터 소유권 | Legal | Boolean | True, False | 이 앱은 업로드 된 데이터의 사용자의 소유권을 보존 완전히? |
| DMCA | Legal | Boolean | True, False | 이 앱은 사용 하 여는 디지털 밀레니엄 저작권 DMCA (), criminalizes 불법 저작권이 있는 자료에 액세스 하려고 하는 준수 합니까? |
| 데이터 보존 정책 | Legal | Boolean | True, False | 계정 종료 후 사용자 데이터 보존에 대 한 앱 정책은 무엇 인가요? |
| GDPR 준비 상태 문 | Legal | URL | 자유 텍스트 | 링크 웹 사이트에 관련 된 경우이 공급자 GDPR 준수를 처리 하도록 계획 하는 방법입니다. |
| 지우기 오른쪽에서 GDPR- | Legal | Boolean | True, False: 해당 없음 | 이 앱 처리를 중지 하 고 요청에 따라 개인의 개인 데이터 삭제? |
| GDPR-데이터 위반 보고서 | Legal | Boolean | True, False: 해당 없음 | 이 앱 보고서 데이터 위반 감독 기관 및 위반 검색의 경우 72 시간 내에서 위반 영향을 받는 개인을 하나요? |
| GDPR-영향 평가 | Legal | Boolean | True, False: 해당 없음 | 이 앱을 개인에 게 위험을 식별 하려면 데이터 보호 영향 평가 수행는? |
| GDPR-보안 교차 테두리 데이터 컨트롤 | Legal | Boolean | True, False: 해당 없음 | 이 앱이 안전 하 게 간에 데이터를 전송 테두리? |
| GDPR-데이터 보호 관리자 | Legal | Boolean | True, False: 해당 없음 | 이 앱 임명 하는 데이터 보호 관리자 데이터 보안 전략 및 GDPR 준수를 감독 하? |
| 개체 오른쪽에서 GDPR- | Legal | Boolean | True, False: 해당 없음 | 이 앱 특정 상황에서 자신의 개인 데이터를 처리 하는 개체 수를 사용 하 여 개인을 제공 하나요? |
| GDPR-오른쪽에 액세스 하려면 | Legal | Boolean | True, False: 해당 없음 | 이 앱 요청 시 회사를 사용 하 여 개인 데이터를 확인 하는 기능 및 사용 하는 방법을 사용 하 여 개인을 제공 하나요? |
| 데이터 Portablility 오른쪽에서 GDPR- | Legal | Boolean | True, False: 해당 없음 | 이 앱 가져오고 요청 시 여러 서비스에서 사용자 용도에 맞게 자신의 개인 데이터를 다시 사용 하는 기능을 사용 하 여 개인을 제공 하나요? |
| GDPR-받아야 오른쪽 | Legal | Boolean | True, False: 해당 없음 | 이 앱 걸리는 이외의 EU 국가 또는 국제적인 조직의 개인 데이터를 전송 하는 경우 적절 한 안전 개인 알리기 위해? |
| 처리 제한 오른쪽에서 GDPR- | Legal | Boolean | True, False: 해당 없음 | 이 앱을 차단 하거나 개인 데이터의 처리를 표시 하지 않을 수 있는 기능을 사용 하 여 개인을 제공 하나요? |
| GDPR-자동화 된 의사 결정을 위해 관련이 권한 | Legal | Boolean | True, False: 해당 없음 | 이 앱 자동화 된 처리에만 기반 하는 의사 결정 될 하지 않도록 선택 하는 기능을 사용 하 여 개인을 제공 하나요? 여기에 프로 파일링 하는 법적 결과 있을 수 있습니다. |
| GDPR-처리를 위해 합법적으로 | Legal | Boolean | True, False: 해당 없음 | 이 앱에 합법적으로 이미 동의 계약, 법적 의무, 중요 한 관심사, 합법적인 관심 분야, 특수 범주, 데이터 및 범죄 행위 데이터에 따라 개인 데이터 처리는? |
| 수정 오른쪽에서 GDPR- | Legal | Boolean | True, False: 해당 없음 | 이 앱의 개인 데이터를 수정 하는 기능을 사용 하 여 개인을 제공 하나요? 컨트롤러는 한 달 내에서 해당 데이터 제공 주체 로부터 모든 요청에 응답 해야 합니다. |


\* 형식의 필드 *배열* 세미콜론 (;)으로 구분 해야 합니다.

## <a name="next-steps"></a>다음 단계 
[클라우드 환경을 보호하는 일상적인 활동](daily-activities-to-protect-your-cloud-environment.md)

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/) 

