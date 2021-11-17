---
emoji: 🛡️
title: AWS WAF(Web Application Firewall)를 이용하여 abusing 유저 IP 로깅하기
date: '2021-11-17 14:50:00'
author: 이영훈
tags: AWS WAF detect_abusing
categories: AWS
---

### 들어가며

한 명이 구글 소셜 회원가입을 다량으로 하는 abusing 문제가 있습니다.

해당 abusing을 막기 위해 해당 IP를 block 시키기로 했습니다.

AWS WAF를 이용하여 회원가입 API 호출하는 IP를 로깅하고 특정 기준에 따라 block하는 방법을 기록으로 남깁니다

### Web ACL 생성

1. AWS WAF & Shield에 들어갑니다

![Screen Shot 2021-11-17 at 1.43.59 PM.png](Screen_Shot_2021-11-17_at_1.43.59_PM.png)

2. 왼쪽 탭에서 `Web ACLs` 에 들어갑니다

3. 원하는 리전을 선택하고 `Create Web ACL` 을 누릅니다 저는 리전을 `Global (CloudFront)` 로 선택하였습니다

   ![Screen Shot 2021-11-17 at 1.47.01 PM.png](Screen_Shot_2021-11-17_at_1.47.01_PM.png)


4. 이름(Name)을 적고 AWS resources를 선택하고 완료되면 Next를 누릅니다

   ![Screen Shot 2021-11-17 at 1.49.24 PM.png](Screen_Shot_2021-11-17_at_1.49.24_PM.png)


5. `Add my own rules and rule groups` 를 선택합니다

   ![Screen Shot 2021-11-17 at 1.50.22 PM.png](Screen_Shot_2021-11-17_at_1.50.22_PM.png)


6. Rule을 작성합니다

   저는 Google social 회원가입을 호출하는 유저의 IP를 탐지하기 위해 `/api/v1/signUp/sns/google` API 요청을 Count하는 Rule을 만들었습니다

   ![Screen Shot 2021-11-17 at 1.53.06 PM.png](Screen_Shot_2021-11-17_at_1.53.06_PM.png)


7. Rule을 넣고 Next를 누릅니다

   ![Screen Shot 2021-11-17 at 1.57.44 PM.png](Screen_Shot_2021-11-17_at_1.57.44_PM.png)

8. Rule의 우선순위를 선택합니다

   ![Screen Shot 2021-11-17 at 1.58.29 PM.png](Screen_Shot_2021-11-17_at_1.58.29_PM.png)


9. CloudWatch에서 모니터링할 Rule을 선택하고, Request 요청을 샘플링 옵션을 선택합니다

   ![Screen Shot 2021-11-17 at 1.58.53 PM.png](Screen_Shot_2021-11-17_at_1.58.53_PM.png)

10. 설정한 ACL을 확인하고 올바르면 생성합니다

   ![Screen Shot 2021-11-17 at 2.00.15 PM.png](Screen_Shot_2021-11-17_at_2.00.15_PM.png)


### 트래픽을 로깅하기

1. 해당 ACL로 들어가서 `Loggin and metrics` 탭으로 이동하고 로깅을 활성화 합니다

   ![Screen Shot 2021-11-17 at 2.02.37 PM.png](Screen_Shot_2021-11-17_at_2.02.37_PM.png)

2. 저는 CloudWatch logs로 로깅하기를 선택합니다

   그리고 현재 CloudWatch Logs의 log group이 없기 때문에 `Create new` 를 눌러 만들어줍니다

   ![Screen Shot 2021-11-17 at 2.03.44 PM.png](Screen_Shot_2021-11-17_at_2.03.44_PM.png)

3. 로그 그룹 이름을 넣어주고 보유 기간(Retention Setting)을 설정합니다

   이름은 반드시 `aws-waf-logs-` 로 시작해야 합니다

   ![Screen Shot 2021-11-17 at 2.08.32 PM.png](Screen_Shot_2021-11-17_at_2.08.32_PM.png)

4. Filter를 설정하고 Save를 합니다

   Count Action에 대해서만 log를 남기고 나머지 로그들은 남기지 않는 설정을 하였습니다

   ![Screen Shot 2021-11-17 at 2.09.56 PM.png](Screen_Shot_2021-11-17_at_2.09.56_PM.png)


5. ACL에 들어와서 CloudWatch Log insights 기능을 사용해서 호출이 많은 IP를 확인합니다

   `Top 100 IP addresses` 를 누르면 다음의 query를 확인할 수 있습니다

   ![Screen Shot 2021-11-17 at 2.13.51 PM.png](Screen_Shot_2021-11-17_at_2.13.51_PM.png)

   쿼리를 실행하면 IP 당 호출 횟수를 알 수 있습니다. IPv4 또는 IPv6가 잡히는 것을 확인할 수 있습니다.

   ![Screen Shot 2021-11-17 at 2.15.30 PM.jpg](Screen_Shot_2021-11-17_at_2.15.30_PM.jpg)
