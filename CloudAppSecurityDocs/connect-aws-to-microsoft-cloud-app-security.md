---
title: "표시 유형 및 사용 제어를 위해 Cloud App Security에 AWS 연결 | Microsoft 문서"
description: "이 항목에서는 API 커넥터를 사용하여 Cloud App Security에 AWS 앱을 연결하는 방법에 대한 정보를 제공합니다."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 68d4c221626706ca641a5d3e1986da543771561a
ms.sourcegitcommit: 0d4748ea2a71e6ee2b0fa1c0498d9219bfbda29a
translationtype: HT
---
# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Microsoft Cloud App Security에 AWS 연결
이 섹션에서는 커넥터 API를 사용하여 기존 Amazon Web Services 계정에 Cloud App Security를 연결하기 위한 지침을 제공합니다.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Cloud App Security에 Amazon 웹 서비스 비교를 연결하는 방법  
  
1.  [Amazon Web Services 콘솔](https://console.aws.amazon.com/)의 **Security, Identity & Compliance**(보안, ID 및 규정 준수)에서 **IAM**을 클릭합니다.  
  
     ![aws ID 및 액세스](./media/aws-identity-and-access.png "aws ID 및 액세스")  
  
2.  **Users**(사용자) 탭을 클릭한 다음 **Add user**(사용자 추가)를 클릭합니다.  
  
     ![aws 사용자](./media/aws-users.png "aws 사용자")      
  
4.  **Details**(세부 정보) 단계에서 Cloud App Security에 대한 새 사용자 이름을 제공하고 **Access type**(액세스 유형)에서 **Programmatic access**(프로그래밍 방식 액세스)를 선택한 후 **Next Permissions**(다음 권한)를 클릭합니다.  

     ![AWS 사용자 만들기](./media/aws-create-user.png "AWS 사용자 만들기")

5. **Permissions**(권한) 단계에서 **Attach existing policies directly**(기존 정책을 바로 연결)를 선택하고 **Create policy**(정책 만들기)를 클릭합니다.

   ![AWS 사용자 연결](./media/aws-attach-user-policy.png "AWS 기존 정책 연결")

6.  **Create Policy**(정책 만들기)에서 **Create Your Own Policy**(고유한 정책 만들기)를 선택합니다.
 
    ![AWS 고유한 정책 만들기](./media/aws-create-own-policy.png "AWS 정책 만들기")
 
7.  **Review Policy**(정책 검토) 아래에 **Policy Name**(정책 이름)을 제공합니다(예: CloudAppSecurityPolicy).

    ![AWS 정책 검토](./media/aws-review-policy.png "AWS 정책 검토")

8. 그런 다음 **Policy Document**(정책 문서) 필드에 다음을 붙여넣고 **Create policy**(정책 만들기)를 클릭합니다.
  
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
  
9. **Add user**(사용자 추가) 화면으로 돌아가서 필요한 경우 목록을 새로 고치고 방금 만든 사용자를 선택한 후 **Next Review**(다음 검토)를 클릭합니다.

   ![AWS 사용자 정책 검토](./media/aws-review-user.png "AWS 사용자 검토")

10. 모든 세부 정보가 올바른 경우 **Create user**(사용자 만들기)를 클릭합니다.

    ![AWS 사용자 권한](./media/aws-user-permissions.png "AWS 사용자 권한 검토")

11. 성공 메시지가 표시되면 **Download .csv**를 클릭하여 새 사용자의 자격 증명 복사본을 저장합니다. 나중에 필요합니다.  

    ![AWS csv 다운로드](./media/aws-download-csv.png "AWS csv 다운로드")
  
10. AWS 콘솔에서 **Services**(서비스)를 클릭하고 **Management Tools**(관리 도구) 아래의 **CloudTrail**을 클릭합니다.  
  
     ![aws cloudtrail](./media/aws-cloudtrail.png "aws cloudtrail")  
  
    이전에 CloudTrail을 사용하지 않은 경우 **Get Started**(시작)를 클릭하고 이름을 제공하고 적절한 S3 버킷을 선택하여 설정한 다음 **Turn On**(켜기)을 클릭합니다. 전체 범위를 적용하려면 **Apply to all regions**(모든 지역에 적용)를 **Yes**(예)로 설정합니다.
  
       ![AWS CloudTrail 켜기](./media/aws-turnon-cloudtrail.png "AWS CloudTrail 켜기")
  
    **Trails**(내역) 목록에 새 CloudTrail 이름이 표시됩니다.
    
      ![AWS CloudTrail 목록](./media/aws-cloudtrail-list.png "AWS CloudTrail 목록")
  
11. Cloud App Security 포털에서 **조사**, **연결된 앱**을 차례로 클릭합니다.  
  
12. **앱 커넥터** 페이지에서 더하기 기호, **AWS**를 차례로 클릭합니다.  
  
     ![AWS 연결](./media/connect-aws.png "AWS 연결")  
  
13. 팝업에서 csv 파일의 **액세스 키** 및 **비밀 키**를 관련 필드에 붙여넣고 **연결**을 클릭합니다.  
   ![AWS 앱 연결](./media/aws-connect-app.png "AWS connect app") 
  
14. **API 테스트**를 클릭하여 연결에 성공했는지 확인합니다.  
  
     테스트는 몇 분 정도 걸릴 수 있습니다. 완료되면 성공 또는 실패 알림을 받게 됩니다. 성공 알림을 받은 후 **완료**를 클릭합니다.  
  
AWS에 연결하면 연결 전 7일 동안 이벤트를 받습니다. CloudTrail을 사용하도록 설정한 경우 CloudTrail를 사용하도록 설정한 시점부터 이벤트를 받습니다.
  
## <a name="see-also"></a>참고 항목  
[정책을 사용하여 클라우드 앱 제어](control-cloud-apps-with-policies.md)   
[기술 지원을 받으려면 Cloud App Security 보조 지원 페이지를 방문하세요.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[프리미어 고객은 프리미어 포털에서 직접 Cloud App Security를 선택할 수도 있습니다.](https://premier.microsoft.com/)  
  
  