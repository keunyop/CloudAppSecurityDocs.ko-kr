---
title: 프록시 뒤에서 로그 수집기 사용 - Cloud App Security | Microsoft Docs
description: 이 문서에서는 프록시 뒤에서 Cloud App Security Cloud Discovery 로그 수집기를 사용하는 방법에 대한 정보를 제공합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 2/2/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 6bde2a6c-60cc-4a7d-9e83-e8b81ac229b0
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: c35ae473569a339b7534d7f70a61467c464d010f
ms.sourcegitcommit: 8ef0438fa35916c48625ff750cb85e9628d202f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56281786"
---
# <a name="enable-the-log-collector-behind-a-proxy"></a>프록시 뒤에서 로그 수집기 사용

로그 수집기를 구성한 후 프록시 뒤에서 실행하는 경우 로그 수집기에서 Cloud App Security로 데이터를 보내는 데 문제가 발생할 수 있습니다. 이 문제는 로그 수집기가 프록시의 루트 인증 기관을 신뢰하지 않고 Microsoft Cloud App Security에 연결하여 구성을 검색하거나 받은 로그를 업로드할 수 없기 때문에 발생할 수 있습니다.

>[!NOTE] 
> Syslog 또는 FTP용 로그 수집기에서 사용하는 인증서를 변경하는 방법과 방화벽 및 프록시와 로그 수집기의 연결 문제를 해결하는 방법에 대한 자세한 내용은 [Microsoft Cloud App Security Cloud Discovery 배포 문제 해결](troubleshoot-docker.md)을 참조하세요.
>

## <a name="set-up-the-log-collector-behind-a-proxy"></a>프록시 뒤에 로그 수집기 설정

Windows 또는 Linux 머신에서 Docker를 실행하는 데 필요한 단계를 수행했으며 머신에 Cloud App Security Docker 이미지를 다운로드했는지 확인합니다. 자세한 내용은 [연속 보고서에 대한 자동 로그 업로드 구성](discovery-docker.md)을 참조하세요.

### <a name="validate-docker-log-collector-container-creation"></a>Docker 로그 수집기 컨테이너 생성 확인

셸에서, 다음 명령을 사용하여 컨테이너가 생성되었고 실행 중인지 확인합니다.

    bash
    docker ps


![docker ps](./media/docker-1.png "docker ps")

### <a name="copy-proxy-root-ca-certificate-to-the-container"></a>프록시 루트 CA 인증서를 컨테이너에 복사

가상 머신에서 CA 인증서를 Cloud App Security 컨테이너에 복사합니다. 다음 예에서 컨테이너는 *Ubuntu LogCollector*로 명명되고 CA 인증서는 *Proxy-CA.crt*로 명명됩니다.
Ubuntu 호스트에서 명령을 실행합니다. 인증서를 실행 중인 컨테이너의 폴더에 복사합니다.

    bash
    docker cp Proxy-CA.crt Ubuntu-LogCollector:/var/adallom/ftp/discovery


### <a name="set-the-configuration-to-work-with-the-ca-certificate"></a>CA 인증서를 사용하도록 구성 설정

1. 다음 명령을 사용하여 컨테이너로 이동합니다. 로그 수집기 컨테이너에서 bash가 열립니다.

        bash
        docker exec -it Ubuntu-LogCollector /bin/bash

2. 컨테이너 내의 bash에서 Java jre 디렉터리로 이동합니다. 버전 관련 경로 오류를 방지하려면 다음 명령을 사용합니다.

       bash
       cd 'find /opt/jdk/*/jre -iname bin'

3. 이전에 복사한 루트 인증서를 *discovery* 폴더에서 Java 키 저장소로 가져오고 암호를 정의합니다. 기본 암호는 “changeit”입니다.

       bash
       ./keytool --import --noprompt --trustcacerts --alias SelfSignedCert --file /var/adallom/ftp/discovery/Proxy-CA.crt --keystore ../lib/security/cacerts --storepass changeit


4. 다음 명령을 사용하여 가져오는 중 제공한 별칭(*SelfSignedCert*)을 검색하여 인증서를 CA 키 저장소로 제대로 가져왔는지 확인합니다.

       bash
       ./keytool --list --keystore ../lib/security/cacerts | grep self


![keytool](./media/docker-2.png "keytool")

가져온 프록시 CA 인증서가 표시됩니다.

### <a name="set-the-log-collector-to-run-with-the-new-configuration"></a>로그 수집기를 새 구성으로 실행되도록 설정

이제 컨테이너는 준비되었습니다. 

로그 수집기 생성 중 사용한 API 토큰을 사용하여 **collector_config** 명령을 실행합니다.

![API 토큰](./media/docker-3.png "API 토큰")

명령을 실행할 때 고유한 API 토큰을 지정합니다.

      bash
      collector_config abcd1234abcd1234abcd1234abcd1234 ${CONSOLE} ${COLLECTOR}


![구성 업데이트](./media/docker-4.png "구성 업데이트")

이제 로그 수집기에서 Cloud App Security와 통신할 수 있습니다. 데이터를 전송하면 Cloud App Security 포털에서 상태가 **정상**에서 **연결됨**으로 변경됩니다.

![상태](./media/docker-5.png "상태")

>[!NOTE]
> 예를 들어 로그 수집기의 구성을 업데이트하거나 데이터 원본을 추가하거나 제거해야 하는 경우 일반적으로 컨테이너를 **삭제**하고 이전 단계를 다시 수행해야 합니다. 그렇게 하지 않으려면 Cloud App Security 포털에서 생성한 새 API 토큰을 사용하여 *collector_config* 도구를 다시 실행하면 됩니다.



 
  
## <a name="next-steps"></a>다음 단계 
[사용자 활동 정책](user-activity-policies.md)   

[프리미어 고객은 프리미어 포털에서 직접 새 지원 요청을 만들 수도 있습니다.](https://premier.microsoft.com/)  
  
  
