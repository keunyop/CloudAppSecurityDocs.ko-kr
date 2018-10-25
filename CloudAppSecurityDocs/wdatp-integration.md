---
title: Windows Defender Advanced Threat Protection을 Cloud App Security에 통합 | Microsoft Docs
description: 이 문서에서는 섀도 IT 및 위험 관리에 대한 Cloud App Security의 원활한 통합 및 향상된 가시성에 Windows Defender ATP를 통합하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/3/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b35ca44c-da8e-49ec-89d1-c076d123c14f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 114e4deeeca06c41132421a748fb95c5c7e7b34d
ms.sourcegitcommit: 53a1c990ff06674c26563a9ebcb1979818c3c063
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48881876"
---
*적용 대상: Microsoft Cloud App Security*


# <a name="windows-defender-advanced-threat-protection-integration-with-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 Windows Defender Advanced Threat Protection 통합

Microsoft Cloud App Security는 Cloud Discovery 롤아웃을 간소화하고, Cloud Discovery 기능을 회사 네트워크 너머로 확장하고, 머신 기반 조사를 사용하기 위해 기본적으로 Windows Defender ATP(Advanced Threat Protection)와 통합됩니다. 

[Windows Defender ATP(Advanced Threat Protection)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)는 지능적인 보호, 감지, 조사 및 대응을 위한 보안 플랫폼입니다. Windows Defender ATP는 사이버 위협으로부터 엔드포인트를 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하고, 보안 태세를 강화합니다.

Microsoft Cloud App Security는 IT 관리 Windows 10 머신에서 액세스하는 클라우드 앱 및 서비스에 대해 Windows Defender ATP에서 수집한 트래픽 정보를 활용합니다. 이를 통해 회사 네트워크의 모든 머신에서 Cloud Discovery를 실행하고, 로밍 동안과 원격 액세스 중에는 공용 Wi-Fi를 사용할 수 있습니다. 또한 머신 기반 조사도 사용할 수 있습니다. 위험한 사용자를 식별한 후에는 해당 사용자가 액세스한 모든 머신에서 잠재적인 위험을 확인할 수 있습니다. 위험한 머신을 식별한 후에는 해당 머신을 사용한 모든 사용자의 잠재적 위험을 확인할 수 있습니다. 엔드포인트에서 Cloud App Security로 라우팅된 로그는 트래픽 활동에 대한 사용자 정보를 제공합니다. Windows Defender ATP 네트워크 작업은 장치 컨텍스트를 제공합니다. 이러한 컨텍스트는 사용자 이름과 결합되어 네트워크의 어떤 머신에서 어떤 사용자가 어떤 작업을 수행했는지에 대한 전체적인 정보를 제공합니다. Microsoft Cloud App Security는 Windows Defender ATP와의 네이티브 통합을 통해 Windows 관리 장치의 클라우드 앱 및 서비스 트래픽 데이터를 활용합니다. 이 원활한 통합에는 추가 배포가 필요하지 않으며 기본 상태로 작동 가능합니다. 엔드포인트에서 트래픽을 라우팅 또는 미러링하거나 복잡한 통합 단계를 수행할 필요가 없습니다.

> [!NOTE]
> Windows Defender ATP를 사용해 보고 싶나요? [평가판 등록](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).
>


## <a name="prerequisites"></a>필수 구성 요소

- Microsoft Cloud App Security 라이선스
- Windows Defender ATP 라이선스
- 버전 1809 이상을 실행하는 Windows 10 머신


## <a name="how-it-works"></a>작동 방식

자체적으로 Cloud App Security는 [사용자가 업로드하는 로그](create-snapshot-cloud-discovery-reports.md)를 사용하여 또는 [자동 로그 업로드를 구성](discovery-docker.md)하여 엔드포인트에서 로그를 수집합니다. 이 네이티브 통합을 사용하면 Windows Defender ATP 에이전트가 Windows에서 실행되고 네트워크 트랜잭션을 모니터링할 때 Windows Defender ATP 에이전트가 만드는 로그를 활용하고, 이러한 로그를 네트워크의 Windows 머신에 수행되는 Shadow IT Discovery에 이용할 수 있습니다. 

다른 플랫폼에서 Cloud Discovery를 수행할 수 있도록 하려면 Cloud App Security [로그 수집기](discovery-docker.md)와 Windows Defender ATP와의 통합을 활용하여 Windows 10 머신을 모니터링하는 것이 가장 좋습니다.


## <a name="how-to-integrate-windows-defender-atp-with-cloud-app-security"></a>Windows Defender ATP를 Cloud App Security와 통합하는 방법

Windows Defender ATP에서 Cloud App Security와 통합하려면:

1. Windows Defender ATP 포털의 탐색 창에서 **기본 설정**을 선택합니다.
2. **설정** 메뉴의 **일반**에서 **고급 기능**을 선택합니다.
3. **Microsoft Cloud App Security**를 **켜짐**으로 전환합니다.
4. **기본 설정 저장**을 클릭합니다.

>[!NOTE]
> 데이터에 대해 설정한 통합이 Cloud App Security에 표시되려면 최대 2시간이 걸립니다.
>

   ![WD ATP 설정](./media/wdatp-settings.png)

## <a name="investigate-machines-in-cloud-app-security"></a>Cloud App Security에서 머신 조사

Windows Defender ATP를 Cloud App Security와 통합한 후에는 Cloud Discovery 대시보드에서 검색된 머신 데이터를 조사할 수 있습니다.

1. Cloud App Security 포털에서 **Cloud Discovery**, **Cloud Discovery 대시보드**를 차례로 클릭합니다.
2. 위의 탐색 모음에 있는 **연속 보고서**에서 **Win10 엔드포인트 사용자**를 선택합니다.
  ![WD ATP 보고서](./media/win10-dashboard-report.png)
4. 통합 이후 검색된 머신 수가 위쪽에 추가된 것을 볼 수 있습니다.
5. **머신** 탭을 클릭합니다.
6. 나열된 각 머신으로 드릴다운하고 탭을 사용하여 조사 데이터를 보고, 인시던트와 관련된 사용자, IP 주소, 앱과 머신 간의 상관 관계를 확인할 수 있습니다.
   - **개요**
      - 트랜잭션: 선택한 기간에 머신에서 발생한 트랜잭션의 수에 대한 정보를 제공합니다.
      - 총 트래픽: 선택한 기간의 총 트래픽양(MB)에 대한 정보를 제공합니다.
     - 업로드: 선택한 기간에 머신이 업로드한 총 트래픽양(MB)에 대한 정보를 제공합니다.
     - 다운로드: 선택한 기간에 머신이 다운로드한 총 트래픽양(MB)에 대한 정보를 제공합니다.
   - **검색된 앱**<br>
  머신에서 액세스한 모든 검색된 앱을 나열합니다.
   - **사용자 기록**<br>
    머신에 로그인한 모든 사용자를 나열합니다.
   - **IP 주소 기록**<br>
    머신에 할당된 모든 IP 주소를 나열합니다.
 ![머신 개요](./media/machines-overview.png)
 

다른 Cloud Discovery 원본과 마찬가지로, 추가 조사를 위해 Win10 엔드포인트 사용자 보고서에서 데이터를 내보낼 수 있습니다. 


## <a name="related-videos"></a>관련 동영상  
[Windows Defender ATP 및 클라우드를 사용하여 회사 네트워크를 벗어난 Shadow IT Discovery](https://www.youtube.com/watch?v=f8hbvbY1Hnc)  

## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
