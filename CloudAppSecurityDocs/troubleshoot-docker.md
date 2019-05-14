---
title: FTP 설정 수정
description: 이 문서에서는 Cloud App Security Cloud Discovery Docker에서 구성을 수정하는 프로세스를 설명합니다.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 04/18/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18
ms.openlocfilehash: bb21ffbef29395ca480fa718ac20f1f372253f23
ms.sourcegitcommit: 9f0c562322394a3dfac7f1d84286e673276a28b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65568625"
---
# <a name="log-collector-ftp-configuration"></a>로그 수집기 FTP 구성

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 Cloud App Security Cloud Discovery Docker에서 구성을 수정하는 방법을 설명합니다.

## <a name="docker-deployment"></a>Docker 배포

Cloud App Security Cloud Discovery Docker에서 구성을 수정해야 합니다. 

### <a name="changing-the-ftp-password"></a>FTP 암호 변경

1. 로그 수집기 호스트에 연결합니다.

2. `docker exec -it <collector name> pure-pw passwd <ftp user>`를 실행합니다.

    1. 새 암호를 입력합니다.
    2. 확인을 위해 새 암호를 다시 입력합니다.
 
3. `docker exec -it <collector name> pure-pw mkdb`를 실행하여 변경 내용을 적용합니다.

  ![ftp 암호 변경](./media/ftp-connect.png)

### <a name="customize-certificate-files"></a>인증서 파일 사용자 지정

이 절차에 따라 Cloud Discovery Docker에 대한 보안 연결에 사용할 인증서 파일을 사용자 지정하세요.

1. FTP 클라이언트를 열고 로그 수집기에 연결합니다.

   ![ftp 클라이언트에 연결](./media/ftp-connect.png)

2. `ssl_update` 디렉터리로 이동합니다.
3. 새 인증서 파일을 `ssl_update` 디렉터리에 업로드합니다(이름은 필수임).

   ![ftp 암호 변경](./media/new-certs.png)

    - **FTP의 경우:** 파일이 하나만 필요합니다. 파일에는 키와 인증서 데이터가 포함되고 차례로 **pure-ftpd.pem**이라고 명명됩니다.
    - **Syslog의 경우:** **ca.pem**, **server-key.pem 및 **server-cert.pem**이라는 세 개의 파일이 필요합니다. 이러한 파일 중 누락되는 파일이 있으면 업데이트가 수행되지 않습니다.

4. 터미널에서 `docker exec -t <collector name> update_certs`를 실행합니다. 이 명령을 실행하면 다음 스크린샷에 표시된 내용과 유사한 출력이 생성됩니다.

   ![ftp 암호 변경](./media/update-certs.png)

## <a name="next-steps"></a>다음 단계

[Cloud Discovery 배포](set-up-cloud-discovery.md)

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)
