---
emoji: ๐ฎ
title: Chapter 4 CPU ์ค์ผ์ค๋ง
date: '2021-10-04 17:30:00'
author: ์ด์ํ
tags: OS Cookbook solution ์๋ฆฌ์ฑ ๋ฌธ์ ํ์ด
categories: OS
---

# Part 2 ํ๋ก์ธ์ค ๊ด๋ฆฌ

## Chapter 4 CPU ์ค์ผ์ค๋ง

### ์์ฝ

1. CPU ์ค์ผ์ค๋ง
    1. CPU ์ค์ผ์ค๋ฌ๋ ํ๋ก์ธ์ค๊ฐ ์์ฑ๋ ํ ์ข๋ฃ๋  ๋๊น์ง ๋ชจ๋  ์ํ ๋ณํ๋ฅผ ์กฐ์ ํ๋ ์ผ์ ํ๋ฉฐ, CPU ์ค์ผ์ค๋ง์ CPU ์ค์ผ์ค๋ฌ๊ฐ ํ๋ ๋ชจ๋  ์์์ ๊ฐ๋ฆฌํจ๋ค.
2. ์ค์ผ์ค๋ง์ ๋จ๊ณ
    1. ๊ณ ์์ค ์ค์ผ์ค๋ง: ์์คํ ๋ด์ ์ ์ฒด ํ๋ก์ธ์ค ์๋ฅผ ์กฐ์ ํ๋ ๊ฒ์ด๋ค.
    2. ์ค๊ฐ ์์ค ์ค์ผ์ค๋ง: ์ ์ฒด ์์คํ์ ํ์ฑํ๋ ํ๋ก์ธ์ค ์๋ฅผ ์กฐ์ ํ์ฌ ๊ณผ๋ถํ๋ฅผ ๋ง๋ ๊ฒ์ด๋ค.
    3. ์ ์์ค ์ค์ผ์ค๋ง: ์ด๋ค ํ๋ก์ธ์ค์ CPU๋ฅผ ํ ๋นํ ์ง, ์ด๋ค ํ๋ก์ธ์ค๋ฅผ ๋๊ธฐ ์ํ๋ก ๋ณด๋ผ ์ง ๋ฑ์ ๊ฒฐ์ ํ๋ ๊ฒ์ด๋ค.
3. ์ค์ผ์ค๋ง์ ๋ชฉ์ 
    1. ๊ณตํ์ฑ: ๋ชจ๋  ํ๋ก์ธ์ค๊ฐ ์์์ ๊ณตํํ๊ฒ ๋ฐฐ์ ๋ฐ์์ผ ํ๋ฉฐ, ์์ ๋ฐฐ์  ๊ณผ์ ์์ ํน์  ํ๋ก์ธ์ค๊ฐ ๋ฐฐ์ ๋์ด์๋ ์ ๋๋ค.
    2. ํจ์จ์ฑ: ์์คํ ์์์ด ์ ํด ์๊ฐ ์์ด ์ฌ์ฉ๋๋๋ก ์ค์ผ์ค๋ง์ ํ๊ณ , ์ ํด ์์์ ์ฌ์ฉํ๋ ค๋ ํ๋ก์ธ์ค์๋ ์ฐ์ ๊ถ์ ์ฃผ์ด์ผ ํ๋ค.
    3. ์์ ์ฑ: ์ฐ์ ์์๋ฅผ ์ฌ์ฉํ์ฌ ์ค์ ํ๋ก์ธ์ค๊ฐ ๋จผ์  ์๋ํ๋๋ก ๋ฐฐ์ ํจ์ผ๋ก์จ ์์คํ ์์์ ์ ์ ํ๊ฑฐ๋ ํ๊ดดํ๋ ค๋ ํ๋ก์ธ์ค๋ก๋ถํฐ ์์์ ๋ณดํธํด์ผ ํ๋ค.
    4. ํ์ฅ์ฑ: ํ๋ก์ธ์ค๊ฐ ์ฆ๊ฐํด๋ ์์คํ์ด ์์ ์ ์ผ๋ก ์๋ํ๋๋ก ์กฐ์นํด์ผ ํ๋ค. ๋ํ ์์คํ ์์์ด ๋์ด๋๋ ๊ฒฝ์ฐ ์ด ํํ์ด ์์คํ์ ๋ฐ์๋๊ฒ ํด์ผ ํ๋ค.
    5. ๋ฐ์ ์๊ฐ ๋ณด์ฅ: ์๋ต์ด ์๋ ๊ฒฝ์ฐ ์ฌ์ฉ์๋ ์์คํ์ด ๋ฉ์ถ ๊ฒ์ผ๋ก ๊ฐ์ ํ๊ธฐ ๋๋ฌธ์ ์์คํ์ ์ ์ ํ ์๊ฐ ์์ ํ๋ก์ธ์ค์ ์๊ตฌ์ ๋ฐ์ํด์ผ ํ๋ค.
    6. ๋ฌดํ ์ฐ๊ธฐ ๋ฐฉ์ง: ํน์  ํ๋ก์ธ์ค์ ์์์ด ๋ฌดํํ ์ฐ๊ธฐ๋์ด์๋ ์ ๋๋ค.
4. ์ค์ผ์ค๋ง ์ ๊ณ ๋ ค ์ฌํญ
    1. ์ฐ์ ์์๊ฐ ๋์ ํ๋ก์ธ์ค์ CPU๋ฅผ ๋จผ์  ํ ๋นํ๋ค.
    2. ์ฐ์ ์์๊ฐ ๋์ ํ๋ก์ธ์ค๋ ์ปค๋ ํ๋ก์ธ์ค, ์ ๋ฉด ํ๋ก์ธ์ค, ๋ํํ ํ๋ก์ธ์ค, ์์ถ๋ ฅ ์ง์ค ํ๋ก์ธ์ค์ด๊ณ 
    3. ์ฐ์ ์์๊ฐ ๋ฎ์ ํ๋ก์ธ์ค๋ ์ผ๋ฐ ํ๋ก์ธ์ค, ํ๋ฉด ํ๋ก์ธ์ค, ์ผ๊ด ์์ ํ๋ก์ธ์ค, CPU ์ง์ค ํ๋ก์ธ์ค์ด๋ค.
5. ๋ค์ค ํ
    1. ํ๋ก์ธ์ค๋ฅผ ํจ์จ์ ์ผ๋ก ๊ด๋ฆฌํ๊ธฐ ์ํด ํ๋ฅผ ์ฌ๋ฌ ๊ฐ ๋์ด ๊ด๋ฆฌํ๋ ๊ฒ์ ๋งํ๋ค.
    2. ์ค๋น ์ํ์์๋ ์ฐ์ ์์์ ๋ฐ๋ผ ๋ค์ค ํ๋ฅผ ์ด์ํ๊ณ 
    3. ๋๊ธฐ ์ํ์์๋ ๊ฐ์ ์์ถ๋ ฅ์ ์๊ตฌํ ํ๋ก์ธ์ค๋ค์ ๋ชจ์ ๋ค์ค ํ๋ฅผ ์ด์ํ๋ค.
6. ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ
    1. FCFS ์ค์ผ์ค๋ง: ์ค๋น ํ์ ๋์ฐฉํ ์์๋๋ก CPU๋ฅผ ํ ๋นํ๋ ๋น์ ์ ํ ์ค์ผ์ค๋ง ๋ฐฉ์์ด๋ค.
    2. SJF ์ค์ผ์ค๋ง: ์ค๋น ํ์ ์๋ ํ๋ก์ธ์ค ์ค์์ ์คํ ์๊ฐ์ด ๊ฐ์ฅ ์งง์ ์์๋ถํฐ CPU๋ฅผ ํ ๋นํ๋ ๋น์ ์ ํ ๋ฐฉ์์ด๋ค.
    3. HRN ์ค์ผ์ค๋ง: CPU๋ฅผ ํ ๋น๋ฐ๊ธฐ ์ํด ๊ธฐ๋ค๋ฆฐ ์๊ฐ๊ณผ CPU ์ฌ์ฉ ์๊ฐ์ ๊ณ ๋ คํ์ฌ ์ค์ผ์ค๋ง์ ํ๋ ๋น์ ์ ํ ๋ฐฉ์์ด๋ค.
    4. ๋ผ์ด๋ ๋ก๋น ์ค์ผ์ค๋ง: ํ ํ๋ก์ธ์ค๊ฐ ํ ๋น๋ฐ์ ์๊ฐ(ํ์ ์ฌ๋ผ์ด๋) ๋์ ์์์ ํ๋ค๊ฐ ์์์ ์๋ฃํ์ง ๋ชปํ๋ฉด ์ค๋น ํ์ ๋งจ ๋ค๋ก ๊ฐ์ ์๊ธฐ ์ฐจ๋ก๋ฅผ ๊ธฐ๋ค๋ฆฌ๋ ์ ์ ํ ๋ฐฉ์์ด๋ค.
    5. SRT ์ค์ผ์ค๋ง: ๊ธฐ๋ณธ์ ์ผ๋ก ๋ผ์ด๋ ๋ก๋น ์ค์ผ์ค๋ง์ ์ฌ์ฉํ์ง๋ง, CPU๋ฅผ ํ ๋น๋ฐ์ ํ๋ก์ธ์ค๋ฅผ ์ ํํ  ๋ ๋จ์ ์๋ ์์ ์๊ฐ์ด ๊ฐ์ฅ ์ ์ ํฌ๋ฅด์ธ์ค๋ฅผ ์ ํํ๋ ์ ์ ํ ๋ฐฉ์์ด๋ค.
    6. ์ฐ์ ์์ ์ค์ผ์ค๋ง: ํ๋ก์ธ์ค๋ ์ค์๋์ ๋ฐ๋ผ ์ฐ์ ์์๋ฅผ ๊ฐ๋๋ฐ ์ด๋ฌํ ์ฐ์ ์์๋ฅผ ๋ฐ์ํ์ฌ CPU๋ฅผ ํ ๋นํ๋ ๋ฐฉ์์ด๋ค. ์ ์ ํ ํน์ ๋น์ ์ ํ ๋ฐฉ์์ผ๋ก ๊ตฌํ์ด ๊ฐ๋ฅํ๋ค.
    7. ๋ค๋จ๊ณ ํ ์ค์ผ์ค๋ง: ์ฐ์ ์์์ ๋ฐ๋ผ ์ค๋น ํ๋ฅผ ์ฌ๋ฌ ๊ฐ ์ฌ์ฉํ๋ ์ ์ ํ ๋ฐฉ์์ด๋ค. ํ๋ก์ธ์ค๋ ์ด์์ฒด์ ๋ก๋ถํฐ ๋ถ์ฌ๋ฐ์ ์ฐ์ ์์์ ๋ฐ๋ผ ํด๋น ์ฐ์ ์์์ ํ์ ์ฝ์๋์ด ์คํ๋๋ค.
    8. ๋ค๋จ๊ณ ํผ๋๋ฐฑ ํ ์ค์ผ์ค๋ง: ๋ค๋จ๊ณ ํ ์ค์ผ์ค๋ง๊ณผ ๊ธฐ๋ณธ์ ์ธ ํํ๊ฐ ๊ฐ์ง๋ง, CPU๋ฅผ ์ฌ์ฉํ๊ณ  ๋ ํ๋ก์ธ์ค๊ฐ ์๋์ ํ๋ก ๋๋์๊ฐ์ง ์๊ณ  ์ฐ์ ์์๊ฐ ํ๋ ๋ฎ์ ํ์ ๋์ผ๋ก ๋ค์ด๊ฐ๋ค.

### ์ฐ์ต๋ฌธ์ 

1. ์์คํ ๋ด ์ ์ฒด ํ๋ก์ธ์ค์ ์๋ฅผ ์กฐ์ ํ๋ ๊ฒ์ผ๋ก, ์ฅ๊ธฐ ์ค์ผ์ค๋ง ๋๋ ์์ ์ค์ผ์ค๋ง์ด๋ผ ๋ถ๋ฆฌ๋ ์ค์ผ์ค๋ง ์์ค์ ๋ฌด์์ธ๊ฐ?
    - ๊ณ ์์ค ์ค์ผ์ค๋ง
2. ์ด๋ค ํ๋ก์ธ์ค์ CPU๋ฅผ ํ ๋นํ๊ณ  ์ด๋ค ํ๋ก์ธ์ค๋ฅผ ๋๊ธฐ ์ํ๋ก ๋ณด๋ผ์ง ๋ฑ์ ๊ฒฐ์ ํ๋ ์ค์ผ์ค๋ง ์์ค์ ๋ฌด์์ธ๊ฐ?
    - ์ ์์ค ์ค์ผ์ค๋ง
3. ์ด๋ค ํ๋ก์ธ์ค๊ฐ CPU๋ฅผ ํ ๋น๋ฐ์ ์คํ ์ค์ด๋๋ผ๋ ์ด์์ฒด์ ๊ฐ CPU๋ฅผ ๊ฐ์ ๋ก ๋นผ์์ ์ ์๋ ์ค์ผ์ค๋ง์ ๋ฌด์์ธ๊ฐ?
    - ์ ์ ํ ์ค์ผ์ค๋ง
4. ํ์ฌ ์์ถ๋ ฅ์ ์งํํ๋ ํ๋ก์ธ์ค๋ก, ์ฌ์ฉ์์ ์ํธ์์์ด ๊ฐ๋ฅํ์ฌ ์ํธ์์ฉ ํ๋ก์ธ์ค๋ผ๊ณ ๋ ๋ถ๋ฆฌ๋ ๊ฒ์ ๋ฌด์์ธ๊ฐ?
    - ๋ํํ ํ๋ก์ธ์ค
5. ์ค๋น ํ์ ๋์ฐฉํ ์์๋๋ก CPU๋ฅผ ํ ๋นํ๋ ๋น์ ์ ํ ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋ฌด์์ธ๊ฐ?
    - FCFS ์ค์ผ์ค๋ง
6. ์ค๋น ํ์ ์๋ ํ๋ก์ธ์ค ์ค ์คํ ์๊ฐ์ด ๊ฐ์ฅ ์งง์ ์์๋ถํฐ CPU๋ฅผ ํ ๋นํ๋ ๋น์ ์ ํ ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋ฌด์์ธ๊ฐ?
    - SJF ์ค์ผ์ค๋ง
7. SJF ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋จ์ ์ผ๋ก ํฌ๊ธฐ๊ฐ ํฐ ์์์ด ๊ณ์ ๋ค๋ก ๋ฐ๋ฆฌ๋ ํ์์ ๋ฌด์์ด๋ผ๊ณ  ํ๋๊ฐ?
    - starvation. ์์ฌ ํ์
8. ์์ฌ ํ์์ ํด๊ฒฐํ๋ ๋ฐฉ๋ฒ์ ์ค๋ชํ์์ค.
    - aging. ํ๋ก์ธ์ค๊ฐ ์๋ณดํ  ์ ์๋ ์ํ์ ์ ์ ํ๋ ๊ฒ์ด๋ค. ์ฆ ํ๋ก์ธ์ค๊ฐ ์์ ์ ์์๋ฅผ ์๋ณดํ  ๋๋ง๋ค ๋์ด๋ฅผ ํ ์ด์ฉ ๋จน์ด ์ต๋ ๋ช ์ด๊น์ง ์๋ณดํ๋๋ก ๊ท์ ํ๋ ๊ฒ์ด๋ค.
9. ์๋น์ค๋ฅผ ๋ฐ๊ธฐ ์ํด ๋๊ธฐํ ์๊ฐ๊ณผ CPU ์ฌ์ฉ ์๊ฐ์ ๊ณ ๋ คํ์ฌ ์ฐ์ ์์๋ฅผ ์ ํ๋ ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋ฌด์์ธ๊ฐ?
    - HRN (Highest Response Ratio Next) ์๊ณ ๋ฆฌ์ฆ. ์ต๊ณ  ์๋ต๋ฅ  ์ฐ์  ์๊ณ ๋ฆฌ์ฆ
10. ํ๋ก์ธ์ค๊ฐ ํ ๋น๋ฐ์ ์๊ฐ(ํ์ ์ฌ๋ผ์ด์ค) ๋์ ์์ํ๋ค๊ฐ ์์์ ์๋ฃํ์ง ๋ชปํ๋ฉด ์ค๋น ํ์ ๋งจ ๋ค๋ก ๊ฐ์ ๋ค์ ์๊ธฐ ์ฐจ๋ก๊ฐ ์ฌ ๋๊น์ง ๊ธฐ๋ค๋ฆฌ๋ ์ ์ ํ ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ ์ค ๊ฐ์ฅ ๋จ์ํ ๊ฒ์ ๋ฌด์์ธ๊ฐ?
    - Round Robin ์๊ณ ๋ฆฌ์ฆ
11. ํ์ ์ฌ๋ผ์ด์ค์ ํฌ๊ธฐ์ ๋ฌธ๋งฅ ๊ตํ์ ๊ด๊ณ๋ฅผ ์ค๋ชํ์์ค.
    - ํ์ ์ฌ๋ผ์ด์ค๊ฐ ๋๋ฌด ํฌ๋ฉด ํ๋์ ์์์ด ๋๋ ๋ค ๋ค์ ์์์ด ์์๋๋ ๊ฒ์ฒ๋ผ ๋ณด์ธ๋ค. ํ๋ก๊ทธ๋จ์ด ๋์์ ์คํ๋์ง ์๋ ๊ฒ์ฒ๋ผ ๋ณด์ฌ ๋ถํธํจ์ ์ด๋ํ๋ค.
    - ํ์ ์ฌ๋ผ์ด์ค๊ฐ ์์ ๊ฒฝ์ฐ, ์ฌ์ฉ์๋ ์ฌ๋ฌ ํ๋ก๊ทธ๋จ์ด ๋์์ ์คํ๋๋ ๊ฒ์ฒ๋ผ ๋๋ ๊ฒ์ด๋ค. ๊ทธ๋ฌ๋ ๋ฌธ๋งฅ ๊ตํ์ด ๋๋ฌด ์์ฃผ ์ผ์ด๋ ๋ฌธ๋งฅ ๊ตํ์ ๊ฑธ๋ฆฌ๋ ์๊ฐ์ด ์ค์  ์์ ์๊ฐ๋ณด๋ค ์๋์ ์ผ๋ก ์ปค์ง๋ฉฐ, ๋ฌธ๋งฅ
      ๊ตํ์ ๋ง์ ์๊ฐ์ ๋ญ๋นํ์ฌ ์ค์  ์์์ ๋ชปํ๋ ๋ฌธ์ ๊ฐ ์๊ธด๋ค.
12. ๊ธฐ๋ณธ์ ์ผ๋ก ๋ผ์ด๋ ๋ก๋น ๋ฐฉ์์ ์ฌ์ฉํ์ง๋ง, CPU๋ฅผ ํ ๋น๋ฐ์ ํ๋ก์ธ์ค๋ฅผ ์ ํํ  ๋ ๋จ์ ์๋ ์์ ์๊ฐ์ด ๊ฐ์ฅ ์ ์ ๊ฒ์ ์ ํํ๋ ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋ฌด์์ธ๊ฐ?
    - SRT (Shortest Remaining Time) ์ค์ผ์ค๋ง
13. ์ฐ์ ์์์ ๋ฐ๋ผ ์ค๋น ํ๋ฅผ ์ฌ๋ฌ ๊ฐ ์ฌ์ฉํ๋ฉฐ ๊ณ ์ ํ ์ฐ์ ์์๋ฅผ ์ ์ฉํ๋ ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋ฌด์์ธ๊ฐ?
    - ๋ค๋จ๊ณ ํ ์ค์ผ์ค๋ง
14. ์ฐ์ ์์์ ๋ฐ๋ผ ์ค๋น ํ๋ฅผ ์ฌ๋ฌ๊ฐ ์ฌ์ฉํ๋ฉฐ, ํ๋ก์ธ์ค๊ฐ CPU๋ฅผ ์ฌ์ฉํ ํ ์ฐ์ ์์๊ฐ ๋ฎ์์ง๋ ํน์ง์ ๊ฐ์ง ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ ๋ฌด์์ธ๊ฐ?
    - ๋ค๋จ๊ณ ํผ๋๋ฐฑ ํ ์ค์ผ์ค๋ง
15. ๋ค๋จ๊ณ ํผ๋๋ฐฑ ํ ์ค์ผ์ค๋ง์์ ๋ง์ง๋ง ํ์ ์๋ ํ๋ก์ธ์ค(์ฐ์ ์์๊ฐ ๊ฐ์ฅ ๋ฎ์ ํ๋ก์ธ์ค)์ ํ์ ์ฌ๋ผ์ด์ค ํฌ๊ธฐ๋ ์ผ๋ง์ธ๊ฐ?
    - ๋ฌดํ๋ (FCFS ์ค์ผ์ค๋ง ๋ฐฉ์์ผ๋ก ๋์)
16. ๋ค๋จ๊ณ ํผ๋๋ฐฑ ํ ์ค์ผ์ค๋ง์์ ์ฐ์ ์์๊ฐ ๋ฎ์์ง์๋ก ํ์ ์ฌ๋ผ์ด์ค์ ํฌ๊ธฐ๋ ์ด๋ป๊ฒ ๋ณํ๋๊ฐ?
    - ๋ค๋จ๊ณ ํผ๋๋ฐฑ ํ ์ค์ผ์ค๋ง์ ์ฐ์ ์์๊ฐ ๋ฎ์ ํ๋ก์ธ์ค์ ์คํ ๊ธฐํ๋ฅผ ํ๋ํ๋ ค๊ณ  ํ์ง๋ง, ๊ทธ๋ ๋ค๊ณ  ํด๋ ์ฐ์ ์์๊ฐ ๋ฎ์ ํ๋ก์ธ์ค๊ฐ ์ฐ์ ์์๊ฐ ๋์ ํ๋ก์ธ์ค๋ณด๋ค CPU๋ฅผ ์ป์ ํ๋ฅ ์ด ์ฌ์ ํ ๋ฎ๋ค. ๋ฐ๋ผ์
      ์ด๋ ต๊ฒ ์ป์ CPU๋ฅผ ์ข ๋ ์ค๋ซ๋์ ์ฌ์ฉํ  ์ ์๋๋ก ์ฐ์ ์์๊ฐ ๋ฎ์ ํ์ ํ์ ์ฌ๋ผ์ด์ค๋ฅผ ํฌ๊ฒ ์ค์ ํ๋ค.
17. ๋ค๋จ๊ณ ํผ๋๋ฐฑ ํ ์ค์ผ์ค๋ง์์ ๋ง์ง๋ง ํ(์ฐ์ ์์๊ฐ ๊ฐ์ฅ ๋ฎ์ ํ)๋ ์ด๋ค ์ค์ผ์ค๋ง ์๊ณ ๋ฆฌ์ฆ์ฒ๋ผ ๋์ํ๋๊ฐ?
    - FCFS ์ค์ผ์ค๋ง
