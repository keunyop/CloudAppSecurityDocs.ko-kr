---
title: "Cloud Discovery Docker 배포 문제 해결 | Microsoft Docs"
description: "이 항목에서는 Cloud App Security Cloud Discovery Docker의 구성을 수정하는 프로세스를 설명합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b994661f0f875db100a0aa2eb293b88e637b89cb
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2018
---
# <a name="troubleshooting-the-cloud-app-security-cloud-discovery-docker"></a>Cloud App Security Cloud Discovery Docker 문제 해결

## <a name="changing-the-ftp-password"></a>FTP 암호 변경


1. 로그 수집기 호스트에 연결합니다.

2.  `docker exec -it <collector name> pure-pw passwd <ftp user>`를 실행합니다.

    1. 새 암호를 입력합니다.
    2. 확인을 위해 새 암호를 다시 입력합니다.
 
3.  `docker exec -it <collector name> pure-pw mkdb`를 실행하여 변경 내용을 적용합니다.


  ![ftp 암호 변경](./media/ftp-connect.png)

## <a name="customize-certificate-files"></a>인증서 파일 사용자 지정

이 절차에 따라 Cloud Discovery Docker에 대한 보안 연결에 사용할 인증서 파일을 사용자 지정하세요.

1.  FTP 클라이언트를 열고 로그 수집기에 연결합니다.

  ![ftp 클라이언트에 연결](./media/ftp-connect.png)

2.  `ssl_update` 디렉터리로 이동합니다.
3.  새 인증서 파일을 `ssl_update` 디렉터리에 업로드합니다(이름은 필수임).

    ![ftp 암호 변경](./media/new-certs.png)

    1.  FTP의 경우: 키와 인증서 데이터를 이 순서대로 포함하는 **pure-ftpd.pem**이라는 단 하나의 파일만 필요합니다.
    
    2.  Syslog의 경우: **ca.pem**, **server-key.pem** 및 **server-cert.pem**이라는 세 개의 파일이 필요합니다. 이러한 파일 중 누락되는 파일이 있으면 업데이트가 수행되지 않습니다.

4.  터미널에서 `docker exec -t <collector name> update_certs`를 실행합니다. 이를 실행하면 다음 화면에 표시된 것과 유사한 출력이 생성됩니다.

    ![ftp 암호 변경](./media/update-certs.png)

## <a name="see-also"></a>참고 항목
[Cloud Discovery 배포](set-up-cloud-discovery.md)

[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)

