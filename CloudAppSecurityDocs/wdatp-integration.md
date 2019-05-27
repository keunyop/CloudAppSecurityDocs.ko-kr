---
title: Cloud App Security를 사용 하 여 Microsoft Defender ATP 통합
description: 이 문서에서는 Cloud App Security를 사용 하 여 섀도 IT 및 위험 관리에 대 한 향상 된 가시성에 대 한 Microsoft Defender Advanced Threat Protection을 통합 하는 방법을 설명 합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/14/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b35ca44c-da8e-49ec-89d1-c076d123c14f
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: b49ab77b33548d6fd188eadde97294ceb6c62ca5
ms.sourcegitcommit: 235b7d5f1f49075c199b154abc38e51326c0493e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66173524"
---
# <a name="microsoft-defender-advanced-threat-protection-integration-with-microsoft-cloud-app-security"></a>Microsoft Cloud App Security를 사용 하 여 Microsoft Defender Advanced Threat Protection 통합

*적용 대상: Microsoft Cloud App Security*

Microsoft Cloud App Security는 기본적으로 사용 하 여 Microsoft Defender ATP Advanced Threat Protection ()를 통합합니다. 통합을 통해 Cloud Discovery의 롤아웃을 간소화하고, Cloud Discovery 기능을 회사 네트워크 외부로 확장하고, 머신 기반 조사를 사용하도록 설정합니다. [Microsoft Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 는 지능형 보호, 검색, 조사 및 응답에 대 한 보안 플랫폼입니다. Microsoft Defender ATP 사이버 위협 으로부터 보호 하는 끝점, 고급 공격 및 데이터 위반을 검색, 보안 인시던트, 자동화 및 보안 상태를 개선 합니다.

Microsoft Cloud App Security는 클라우드 앱 및 Windows 10 IT 관리 컴퓨터에서 액세스 하는 서비스에 대 한 Microsoft Defender ATP에서 수집 되는 트래픽 정보를 사용 합니다. 이 통합을 통해 회사 네트워크의 머신에서 Cloud Discovery를 실행하고, 로밍하는 동안 원격 액세스를 통해 공용 Wi-Fi를 사용할 수 있습니다. 머신 기반 조사를 사용할 수도 있습니다.

위험한 사용자를 식별하면 잠재적인 위험을 감지하기 위해 사용자가 액세스한 모든 머신을 확인할 수 있습니다. 위험한 머신을 식별하면 잠재적인 위험을 감지하기 위해 사용된 모든 사용자를 확인하세요. 엔드포인트에서 Cloud App Security로 라우팅된 로그는 트래픽 활동에 대한 사용자 정보를 제공합니다. Microsoft Defender ATP 네트워크 활동 장치 컨텍스트를 제공합니다. 사용자 이름을 포함한 디바이스 컨텍스트를 페어링하여 어떤 사용자가 어떤 머신에서 어떤 작업을 수행하는지 네트워크를 통해 전체적인 내용을 제공합니다.

Microsoft Cloud App Security 관리 되는 Windows 장치에서 클라우드 앱 및 서비스 트래픽에 대 한 데이터를 Microsoft Defender ATP를 사용 하 여 네이티브 통합을 사용 합니다. 이 통합에는 추가 배포가 필요하지 않으며 기본 상태로 작동합니다. 엔드포인트에서 트래픽을 라우팅 또는 미러링하거나 복잡한 통합 단계를 수행할 필요가 없습니다.

> [!NOTE]
> Microsoft Defender ATP를 경험 하 시겠습니까? [평가판 등록](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).
>


## <a name="prerequisites"></a>필수 구성 요소

- Microsoft Cloud App Security 라이선스
- Microsoft Defender ATP 라이선스
- 버전 1809 이상을 실행하는 Windows 10 머신
- Cloud App Security에서 이 기능을 사용하려면 **미리보기능** 켜세요.

## <a name="how-it-works"></a>작동 방법

자체적으로 Cloud App Security는 [사용자가 업로드하는 로그](create-snapshot-cloud-discovery-reports.md)를 사용하여 또는 [자동 로그 업로드를 구성](discovery-docker.md)하여 엔드포인트에서 로그를 수집합니다. 네이티브 통합을 사용 하면 Microsoft Defender ATP 에이전트 만듭니다 Windows에서 실행 될 때 로그를 활용할 수 있습니다 하 고 모니터 네트워크 트랜잭션. 이러한 정보를 네트워크의 Windows 머신 간에 수행되는 Shadow IT Discovery에 사용합니다.

을 다른 플랫폼에서 Cloud Discovery를 수행할 수 있도록 하는 것이 좋습니다 모두 Cloud App Security를 사용 하도록 [로그 수집기](discovery-docker.md), Windows 10 컴퓨터를 모니터링 하려면 Microsoft Defender ATP 통합 함께 합니다.

## <a name="how-to-integrate-microsoft-defender-atp-with-cloud-app-security"></a>Cloud App Security를 사용 하 여 Microsoft Defender ATP를 통합 하는 방법

사용 하려면 Microsoft Defender ATP에서 Cloud App Security와 통합:

1. Microsoft Defender ATP 포털의 탐색 창에서 선택 **기본 설정 설치**합니다.
2. **설정** 메뉴의 **일반**에서 **고급 기능**을 선택합니다.
3. **Microsoft Cloud App Security**를 **켜짐**으로 전환합니다.
4. **기본 설정 저장**을 클릭합니다.

>[!NOTE]
> 데이터에 대해 설정한 통합이 Cloud App Security에 표시되려면 최대 2시간이 걸립니다.
>

   ![WD ATP 설정](./media/wdatp-settings.png)

## <a name="investigate-machines-in-cloud-app-security"></a>Cloud App Security에서 머신 조사

Cloud App Security를 사용 하 여 Microsoft Defender ATP를 통합 한 후에 Cloud Discovery 대시보드에서 검색 된 컴퓨터 데이터를 조사할 수 있습니다.

1. Cloud App Security 포털에서 **Cloud Discovery**, **Cloud Discovery 대시보드**를 차례로 클릭합니다.
2. 위의 탐색 모음에 있는 **연속 보고서**에서 **Win10 엔드포인트 사용자**를 선택합니다.
  ![WD ATP 보고서](./media/win10-dashboard-report.png)
3. 통합 이후 검색된 머신 수가 위쪽에 추가된 것을 볼 수 있습니다.
4. **머신** 탭을 클릭합니다.
5. 나열된 각 머신에 드릴다운하고 조사 데이터를 보는 탭을 사용할 수 있습니다. 인시던트에 관련된 머신, 사용자, IP 주소 및 앱 간의 상관 관계를 찾습니다.
   - **개요**
      - 트랜잭션: 선택한 기간 동안 머신에서 발생한 트랜잭션의 수에 대한 정보입니다.
      - 총 트래픽: 선택한 기간 동안 총 트래픽(MB)에 대한 정보입니다.
     - 업로드: 선택한 기간 동안 머신이 업로드한 총 트래픽(MB)에 대한 정보입니다.
     - 다운로드: 선택한 기간 동안 머신이 다운로드한 총 트래픽(MB)에 대한 정보입니다.
   - **검색된 앱**<br>
  머신에서 액세스한 모든 검색된 앱을 나열합니다.
   - **사용자 기록**<br>
    머신에 로그인한 모든 사용자를 나열합니다.
   - **IP 주소 기록**<br>
    머신에 할당된 모든 IP 주소를 나열합니다.
 ![머신 개요](./media/machines-overview.png)
 
다른 Cloud Discovery 원본과 마찬가지로, 추가 조사를 위해 Win10 엔드포인트 사용자 보고서에서 데이터를 내보낼 수 있습니다. 

> [!NOTE]
> - Defender ATP ~ 4MB((트랜잭션 ~ 4000 개 끝점)의 청크를 Cloud App Security 데이터 전달
> - 4MB 제한 되지 않습니다 1 시간 내에 도달 하면 지난 시간 동안의 Defender ATP 보고서 모든 트랜잭션을 수행 합니다.

## <a name="related-videos"></a>관련 동영상

[Microsoft Defender ATP와 Cloud App Security를 사용 하 여 회사 네트워크 이외의 섀도 IT 검색](https://www.youtube.com/watch?v=f8hbvbY1Hnc)  

## <a name="next-steps"></a>다음 단계 
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md) 

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
