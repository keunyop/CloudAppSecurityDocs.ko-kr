---
title: IP 범위 및 태그 설정 | Microsoft 문서
description: 이 문서에서는 IP 태그 및 IP 범주 사용에 관한 지침을 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/16/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: bbf54f66-4ce2-428c-afc8-b5a64277014f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d21d85e9868fa0e9546bdc893dfc16036af93615
ms.sourcegitcommit: 851ff017c226435d38bed18dbece640a632cd2a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2018
ms.locfileid: "51943721"
---
#  <a name="IPtagsandRanges"></a> IP 범위 및 태그 사용

*적용 대상: Microsoft Cloud App Security*

실제 사무실 IP 주소와 같이 알려진 IP 주소를 쉽게 식별하려면 IP 주소 범위를 설정해야 합니다. IP 주소 범위를 사용하면 로그 및 경고가 표시되고 조사되는 방식을 태그 지정, 분류 및 사용자 지정할 수 있습니다. IP 범위의 각 그룹은 사전 설정된 IP 범주 목록에 따라 분류할 수 있습니다. IP 범위에 대한 사용자 지정 IP 태그를 만들 수도 있습니다. 또한 내부 네트워크 지식에 따라 공용 지리적 위치 정보를 재정의할 수 있습니다. IPv4 및 IPv6 모두 지원됩니다. 

Cloud App Security는 Azure 및 Office 365와 같이 널리 사용되는 클라우드 공급자를 위해 내장 IP 범위가 사전 구성되어 제공됩니다. 또한 익명 프록시, 봇네트 및 Tor를 포함한 Microsoft 위협 인텔리전스를 기반으로 하는 태그가 기본 제공되어 있습니다. IP 주소 범위 페이지의 드롭다운에서 전체 목록을 볼 수 있습니다.

> [!NOTE]
> - 검색의 일부로 이러한 기본 제공 태그를 사용하려면 Cloud App Security API 설명서에서 해당 ID를 참조하세요. 
> - **IP 주소 범위 API**를 사용하여 스크립트를 만들어 IP 범위를 대량으로 추가할 수 있습니다. 
> - API 설명서를 보려면 Cloud App Security 포털 메뉴 모음에서 물음표를 클릭한 다음, **API 설명서**를 클릭합니다.


기본 제공 IP 주소 태그 및 사용자 지정 IP 태그는 계층적으로 간주됩니다. 사용자 지정 IP 태그가 기본 제공 IP 태그보다 우선합니다. 예를 들어 IP 주소를 위협 인텔리전스에 따라 **위험**으로 태그 지정하지만 **회사**로 식별하는 사용자 지정 IP 태그가 있는 경우, 사용자 지정 범주 및 태그가 우선순위로 적용됩니다.

## <a name="create-an-ip-address-range"></a>IP 주소 범위 만들기 

메뉴 모음에서 설정 아이콘을 클릭합니다. **IP 주소 범위**를 선택합니다. 더하기 기호를 클릭하여 IP 주소 범위를 추가하고 다음 필드를 설정합니다.  

  
1. IP 범위에 **이름**을 지정합니다. 이 이름은 활동 로그에 표시되지 않고 IP 범위를 관리하는 데만 사용됩니다.  
  
     IP 범위를 IP 범주에 포함하려면 드롭다운 메뉴에서 범주를 선택합니다.  
  
2. 구성하려는 **IP 주소 범위**를 입력하고 "+" 단추를 클릭합니다. 네트워크 접두사 표기법(CIDR 표기법이라고도 함, 예: 192.168.1.0/32)을 사용하여 IP 주소 및 서브넷을 원하는 개수만큼 추가할 수 있습니다.  
  
3. **범주**는 관심 있는 IP 주소의 활동을 쉽게 인식하는 데 사용됩니다. 범주는 포털에서 사용할 수 있습니다. 그러나 일반적으로 각 범주에 포함되는 IP 주소를 확인하려면 사용자 구성이 필요합니다. 이 구성의 예외는 "위험" 범주로서, 익명 프로시와 Tor라는 두 개의 IP 태그를 포함합니다.  
  
     다음 IP 범주를 사용할 수 있습니다.  
  
    - **관리**: 관리자의 모든 IP 주소여야 합니다.  
  
    - **클라우드 공급자**: 클라우드 공급자에서 사용하는 IP 주소여야 합니다.
  
    - **회사**: 내부 네트워크, 지점 및 Wi-Fi 로밍 주소의 모든 IP 주소여야 합니다.  
  
    - **위험**: 위험한 것으로 간주하는 모든 IP 주소여야 합니다. 여기에는 과거에 본 적이 있는 의심스러운 IP 주소, 경쟁업체의 네트워크에 있는 IP 주소 등이 포함될 수 있습니다.  
  
    - **VPN**: 원격 작업자에 사용하는 모든 IP 주소여야 합니다.
  
4. 이러한 IP 주소의 작업에 **태그**를 지정하려면 태그를 입력합니다. 상자에 단어를 입력하면 태그가 생성됩니다. 이미 구성된 태그가 있으면 목록에서 선택하여 다른 IP 범위에 쉽게 추가할 수 있습니다. 각 범위에 대해 IP 태그를 원하는 개수만큼 추가할 수 있습니다. 정책을 만들 때 IP 태그를 사용할 수 있습니다.  구성하는 IP 태그와 함께 Cloud App Security에는 구성할 수 없는 기본 제공 태그가 있습니다. [IP 태그 필터](activity-filters.md) 아래에서 태그의 목록을 볼 수 있습니다.  
    > [!NOTE]  
    > - 위치 및 등록된 ISP가 기본값을 재정의합니다.
    > - IP 태그는 데이터를 재정의하지 않고 활동에 추가됩니다.

5. 이러한 주소의 **위치** 또는 조직(ISP) 필드를 재정의하려면 새 값을 입력합니다. 예를 들어 아일랜드에 공개적으로 있는 것으로 간주되는 IP 주소가 있다고 가정해 봅니다. 그러나 IP가 미국에 있다는 것을 알고 있습니다. 해당 IP 주소 범위에 대한 위치를 재정의합니다.  
  
6. **등록된 ISP**를 입력합니다. 이 설정은 활동의 데이터를 재정의합니다.  
 
7. 완료되면 **만들기**를 클릭합니다.  
  
     ![newipaddress 범위](./media/newipaddress-range.png "newipaddress 범위")  


## <a name="next-steps"></a>다음 단계
[Cloud Discovery 설정](set-up-cloud-discovery.md)   

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  