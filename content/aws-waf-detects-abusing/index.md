---
emoji: ๐ก๏ธ
title: AWS WAF(Web Application Firewall)๋ฅผ ์ด์ฉํ์ฌ abusing ์ ์  IP ๋ก๊นํ๊ธฐ
date: '2021-11-17 14:50:00'
author: ์ด์ํ
tags: AWS WAF detect_abusing
categories: AWS
---

### ๋ค์ด๊ฐ๋ฉฐ

ํ ๋ช์ด ๊ตฌ๊ธ ์์ ํ์๊ฐ์์ ๋ค๋์ผ๋ก ํ๋ abusing ๋ฌธ์ ๊ฐ ์์ต๋๋ค.

ํด๋น abusing์ ๋ง๊ธฐ ์ํด ํด๋น IP๋ฅผ block ์ํค๊ธฐ๋ก ํ์ต๋๋ค.

AWS WAF๋ฅผ ์ด์ฉํ์ฌ ํ์๊ฐ์ API ํธ์ถํ๋ IP๋ฅผ ๋ก๊นํ๊ณ  ํน์  ๊ธฐ์ค์ ๋ฐ๋ผ blockํ๋ ๋ฐฉ๋ฒ์ ๊ธฐ๋ก์ผ๋ก ๋จ๊น๋๋ค

### Web ACL ์์ฑ

1. AWS WAF & Shield์ ๋ค์ด๊ฐ๋๋ค

![Screen Shot 2021-11-17 at 1.43.59 PM.png](Screen_Shot_2021-11-17_at_1.43.59_PM.png)

2. ์ผ์ชฝ ํญ์์ `Web ACLs` ์ ๋ค์ด๊ฐ๋๋ค

3. ์ํ๋ ๋ฆฌ์ ์ ์ ํํ๊ณ  `Create Web ACL` ์ ๋๋ฆ๋๋ค ์ ๋ ๋ฆฌ์ ์ `Global (CloudFront)` ๋ก ์ ํํ์์ต๋๋ค

   ![Screen Shot 2021-11-17 at 1.47.01 PM.png](Screen_Shot_2021-11-17_at_1.47.01_PM.png)


4. ์ด๋ฆ(Name)์ ์ ๊ณ  AWS resources๋ฅผ ์ ํํ๊ณ  ์๋ฃ๋๋ฉด Next๋ฅผ ๋๋ฆ๋๋ค

   ![Screen Shot 2021-11-17 at 1.49.24 PM.png](Screen_Shot_2021-11-17_at_1.49.24_PM.png)


5. `Add my own rules and rule groups` ๋ฅผ ์ ํํฉ๋๋ค

   ![Screen Shot 2021-11-17 at 1.50.22 PM.png](Screen_Shot_2021-11-17_at_1.50.22_PM.png)


6. Rule์ ์์ฑํฉ๋๋ค

   ์ ๋ Google social ํ์๊ฐ์์ ํธ์ถํ๋ ์ ์ ์ IP๋ฅผ ํ์งํ๊ธฐ ์ํด `/api/v1/signUp/sns/google` API ์์ฒญ์ Countํ๋ Rule์ ๋ง๋ค์์ต๋๋ค

   ![Screen Shot 2021-11-17 at 1.53.06 PM.png](Screen_Shot_2021-11-17_at_1.53.06_PM.png)


7. Rule์ ๋ฃ๊ณ  Next๋ฅผ ๋๋ฆ๋๋ค

   ![Screen Shot 2021-11-17 at 1.57.44 PM.png](Screen_Shot_2021-11-17_at_1.57.44_PM.png)

8. Rule์ ์ฐ์ ์์๋ฅผ ์ ํํฉ๋๋ค

   ![Screen Shot 2021-11-17 at 1.58.29 PM.png](Screen_Shot_2021-11-17_at_1.58.29_PM.png)


9. CloudWatch์์ ๋ชจ๋ํฐ๋งํ  Rule์ ์ ํํ๊ณ , Request ์์ฒญ์ ์ํ๋ง ์ต์์ ์ ํํฉ๋๋ค

   ![Screen Shot 2021-11-17 at 1.58.53 PM.png](Screen_Shot_2021-11-17_at_1.58.53_PM.png)

10. ์ค์ ํ ACL์ ํ์ธํ๊ณ  ์ฌ๋ฐ๋ฅด๋ฉด ์์ฑํฉ๋๋ค

   ![Screen Shot 2021-11-17 at 2.00.15 PM.png](Screen_Shot_2021-11-17_at_2.00.15_PM.png)


### ํธ๋ํฝ์ ๋ก๊นํ๊ธฐ

1. ํด๋น ACL๋ก ๋ค์ด๊ฐ์ `Loggin and metrics` ํญ์ผ๋ก ์ด๋ํ๊ณ  ๋ก๊น์ ํ์ฑํ ํฉ๋๋ค

   ![Screen Shot 2021-11-17 at 2.02.37 PM.png](Screen_Shot_2021-11-17_at_2.02.37_PM.png)

2. ์ ๋ CloudWatch logs๋ก ๋ก๊นํ๊ธฐ๋ฅผ ์ ํํฉ๋๋ค

   ๊ทธ๋ฆฌ๊ณ  ํ์ฌ CloudWatch Logs์ log group์ด ์๊ธฐ ๋๋ฌธ์ `Create new` ๋ฅผ ๋๋ฌ ๋ง๋ค์ด์ค๋๋ค

   ![Screen Shot 2021-11-17 at 2.03.44 PM.png](Screen_Shot_2021-11-17_at_2.03.44_PM.png)

3. ๋ก๊ทธ ๊ทธ๋ฃน ์ด๋ฆ์ ๋ฃ์ด์ฃผ๊ณ  ๋ณด์  ๊ธฐ๊ฐ(Retention Setting)์ ์ค์ ํฉ๋๋ค

   ์ด๋ฆ์ ๋ฐ๋์ `aws-waf-logs-` ๋ก ์์ํด์ผ ํฉ๋๋ค

   ![Screen Shot 2021-11-17 at 2.08.32 PM.png](Screen_Shot_2021-11-17_at_2.08.32_PM.png)

4. Filter๋ฅผ ์ค์ ํ๊ณ  Save๋ฅผ ํฉ๋๋ค

   Count Action์ ๋ํด์๋ง log๋ฅผ ๋จ๊ธฐ๊ณ  ๋๋จธ์ง ๋ก๊ทธ๋ค์ ๋จ๊ธฐ์ง ์๋ ์ค์ ์ ํ์์ต๋๋ค

   ![Screen Shot 2021-11-17 at 2.09.56 PM.png](Screen_Shot_2021-11-17_at_2.09.56_PM.png)


5. ACL์ ๋ค์ด์์ CloudWatch Log insights ๊ธฐ๋ฅ์ ์ฌ์ฉํด์ ํธ์ถ์ด ๋ง์ IP๋ฅผ ํ์ธํฉ๋๋ค

   `Top 100 IP addresses` ๋ฅผ ๋๋ฅด๋ฉด ๋ค์์ query๋ฅผ ํ์ธํ  ์ ์์ต๋๋ค

   ![Screen Shot 2021-11-17 at 2.13.51 PM.png](Screen_Shot_2021-11-17_at_2.13.51_PM.png)

   ์ฟผ๋ฆฌ๋ฅผ ์คํํ๋ฉด IP ๋น ํธ์ถ ํ์๋ฅผ ์ ์ ์์ต๋๋ค. IPv4 ๋๋ IPv6๊ฐ ์กํ๋ ๊ฒ์ ํ์ธํ  ์ ์์ต๋๋ค.

   ![Screen Shot 2021-11-17 at 2.15.30 PM.jpg](Screen_Shot_2021-11-17_at_2.15.30_PM.jpg)
