---
title: "AWS 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 AWS 앱을 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6beb9041b338406fb5b16f4bd045dbdc4592c6d9
ms.openlocfilehash: a56257b7c149c3ea054f200ef88df0ab41b7e25b


---

# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 AWS 연결
이 섹션에서는 커넥터 API를 사용하여 기존 Amazon Web Services 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Cloud App Security에 Amazon 웹 서비스 비교를 연결하는 방법  
  
1.  Amazon 웹 서비스 비교 콘솔에서 **ID 및 액세스 관리**를 클릭합니다.  
  
     ![aws ID 및 액세스](./media/aws-identity-and-access.png "aws identity and access")  
  
2.  **사용자** 탭을 클릭합니다.  
  
     ![aws 사용자](./media/aws-users.png "aws users")  
  
3.  **새 사용자 만들기**를 클릭합니다.  
  
     ![AWS 사용자 만들기](./media/aws-create-user.png "AWS create user")  
  
4.  Cloud App Security에 대한 새 사용자를 만들고 **각 사용자에 대한 액세스 키 생성** 확인란이 선택되었는지 확인합니다.  
  
5.  **자격 증명 다운로드**를 클릭합니다.  
  
     ![aws dl 자격 증명](./media/aws-dl-cred.png "aws dl cred")  
  
6.  **사용 권한** 탭에서 **Attach Policy**(정책 연결)를 클릭합니다.  
  
     ![aws 사용자 정책 연결](./media/aws-attach-user-policy.png "aws attach user policy")  
  
7.  **정책 검토** 화면이 열립니다.
 
     ![정책 검토](./media/aws-review-policy.png "aws review policy")  
  

8. **정책 이름** 아래에 "AdallomTrustPolicy"를 입력합니다. 
10. **Policy Document**(정책 문서) 아래에서 다음을 복사하여 붙여 넣습니다.  
  
    ```     
    {  
      "Version" : "2012-10-17",  
      "Statement" : [{  
          "Action" : [  
            "cloudtrail:DescribeTrails",  
  
           "cloudtrail:LookupEvents",  
            "cloudtrail:GetTrailStatus",  
            "cloudwatch:Describe*",  
            "cloudwatch:Get*",  
            "cloudwatch:List*",  
            "iam:List*",  
            "iam:Get*"  
          ],  
          "Effect" : "Allow",  
          "Resource" : "*"  
        }  
      ]  
     }  
  
    ```  
  
9. 다운로드한 파일 `credentials.csv`에서 새 사용자의 자격 증명을 찾습니다. 나중에 이러한 자격 증명을 복사해야 합니다.  
  
10. AWS 콘솔 기본 페이지로 돌아가서 오른쪽 위에 있는 드롭다운 창을 통해 주 영역을 선택한 다음 주 메뉴에서 **CloudTrail**을 클릭합니다.  
  
     ![aws cloudtrail](./media/aws-cloudtrail.png "aws cloudtrail")  
  
    1.  이전에 이 영역에 CloudTrail을 사용하지 않은 경우 **시작** 단추를 클릭하고 적절한 S3 버킷을 선택하여 설정합니다.  
  
         화면 왼쪽에서 **구성** 탭을 클릭합니다. **추가 구성**에서 편집 아이콘을 클릭합니다.  
  
         ![aws cloudtrail 구성](./media/aws-cloudtrail-config.png "aws cloudtrail config")  
  
    2.  **글로벌 서비스 포함** 여부를 묻는 메시지가 표시되면 **예**를 클릭한 다음 **저장**을 클릭합니다. 이 설정은 선택한 영역에만 적용됩니다.  
  
         ![aws 글로벌 서비스 포함](./media/aws-include-global-svc.png "aws include global svc")  
  
    3.  모든 영역에 대해 11단계를 반복하되 글로벌 서비스를 포함하도록 다른 영역을 설정하지 마세요.  
  
11. Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
12. **앱 커넥터** 페이지에서 더하기 기호, **AWS**를 차례로 클릭합니다.  
  
     ![AWS 연결](./media/connect-aws.png "connect AWS")  
  
13. 팝업에서 csv 파일의 **액세스 키** 및 **비밀 키**를 API 페이지의 필드에 붙여넣고 **액세스 키 업데이트**를 클릭합니다.  
  
14. **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 완료되면 성공 또는 실패 알림을 받게 됩니다. 성공 알림을 받은 후 **완료**를 클릭합니다.  
  
AWS를 연결한 후 연결 전 7일에 대한 이벤트를 받게 됩니다.
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


