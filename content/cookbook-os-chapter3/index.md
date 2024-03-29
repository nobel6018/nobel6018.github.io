---
emoji: 🔮
title: Chapter 3 프로세스와 스레드
date: '2021-09-22 20:00:00'
author: 이영훈
tags: OS Cookbook solution 요리책 문제풀이
categories: OS
---

# Part 2 프로세스 관리

## Chapter 3 프로세스와 스레드

### 요약

1. 프로그램과 프로세스
    1. 프로그램은 저장장치에 저장되어 있는 정적인 상태
    2. 프로세스는 실행을 위해 메모리에 올라온 동적인 상태
2. 프로세스의 상태
    1. 생성 상태: 프로그래을 메모리에 가져와 실행 준비가 완료된 상태이다.
    2. 준비 상태: 실행을 기다리는 모든 프로세스가 자기 차례를 기다리는 상태이다. 실행될 프로세스를 CPU 스케줄러가 선택한다.
    3. 실행 상태: 선택된 프로세스가 타임 슬라이스를 얻어 CPU를 사용하는 상태이다. 프로세스 사이의 문맥 교환이 일어난다.
    4. 대기 상태: 실행 상태에 있는 프로세스가 입출력을 요청하면 입출력이 완료될 때까지 기다리는 상태이다. 입출력이 완료되면 준비 상태로 간다.
    5. 완료 상태: 프로세스가 종료된 상태이다. 사용하던 모든 데이터갖 ㅓㅇ리된다. 정상 종료인 exit와 비정상 종료인 abort를 포함한다.
3. 프로세스 제어 블록
    1. 프로세스를 실행하는 데 필요한 중요한 정보를 보관하는 자료 구조로, 모든 프로세스는 고유의 프로세스 제어 블록을 가진다.
    2. 프로세스 제어 블록은 프로세스 생성 시 만들어져서 프로세스가 실행을 완료하면 폐기된다.
4. 문맥 교환
    1. 두 프로세스의 프로세스 제어 블록 및 이와 관련된 값들을 교환하는 작업을 말한다.
    2. 일반적으로 문맥 교환은 한 프로세스가 자신에게 주어진 시간을 다 사용하면 발생하고, 인터럽트가 걸렸을 때도 발생한다.
5. 프로세스의 복사와 전환
    1. fork() 시스템 호출: 실행 중인 프로세스로부터 새로운 프로세스를 복사하는 함수이다.
    2. exec() 시스템 호출: 기존의 프로세스를 새로운 프로세스로 전환하는 함수이다.
6. 프로세스의 계층 구조
    1. 부모 프로세스를 복사하여 자식 프로세스를 만드는 방법으로 프로세스끼리 계층 구조를 갖는 것을 말한다.
    2. 부모 프로세스는 자신의 자원을 자식 프로세스에 상속하고 자식 프로세스가 종료되면 그 자원을 회수한다.
7. 스레드
    1. CPU 스케줄러가 CPU에 전달하는 일 하나를 스레드라고 하며, 하나의 프로세스에는 여러 개의 스레드가 존재하기도 한다.
8. 스레드 관련 용어
    1. 멀티스레드: 멀티스레드는 프로세스 내 작업을 여러 개 스레드로 분할함으로써 작업의 부담을 줄이는 프로세스 운영 기법이다.
    2. 멀티태스킹: 운영체제가 CPU에 작업을 줄 때 시간을 잘게 나누어 배분하는 기법이다.
    3. 멀티프로세싱: CPU를 여러 개 사용하여 여러 개의 스레드를 동시에 처리하는 작업 환경을 말한다.
    4. CPU 멀티스레드: 한 번에 하나씩 처리해야 하는 스레드를 파이프라인 기법을 이용하여 동시에 여러 스레드를 처리하도록 만든 병렬 처리 기법이다.
9. 멀티스레드의 장점
    1. 응답성 향상: 한 스레드가 입출력으로 인해 작업이 진행되지 않더라도 다른 스레드가 작업을 계속하여 사용자의 작업 요구에 빨리 응답할 수 있다.
    2. 자원 공유: 한 프로세스 내에서 독립적인 스레드를 생성하면 프로세스가 가진 자원을 모든 스레드가 공유하게 되어 작업을 원할하게 진행할 수 있다.
    3. 효율성 향상: 불필요한 자원의 중복을 막음으로써 시스템의 효율이 향상된다.
    4. 다중 CPU 지원: 2개 이상의 CPU를 가진 컴퓨터에서 멀티스레드를 사용하면 다중 CPU가 멀티스레드를 동시에 처리하여 CPU 사용량이 증가하고 프로세스의 처리 시간이 단축된다.
10. 멀티스레드 모델
    1. 사용자 스레드: 사용자 레벨에서 관련 라이브러리를 사용하여 구현하며, 라이브러리는 커널이 지원하는 스케줄링이나 동기화 같은 기능을 대신 구현해준다.
    2. 커널 스레드: 커널이 멀티스레드를 지원하는 방식이다.
    3. 멀티레벨 스레드: 사용자 스레드와 커널 스레드를 혼합한 방식으로 하이브리등 스레드라고도 한다.

### 연습문제

1. 프로그램이 프로세스가 되려면 운영체제로부터 무엇을 받아야 하는가?
   - PCB (Process Control Block)
2. 프로세스의 상태 중 CPU를 할당받기 위해 기다리는 상태는 무엇인가?
   - 준비상태
3. 프로세스의 상태 중 입출력 작업을 하기 위해 이동하는 상태는 무엇인가?
   - 대기상태
4. CPU 스케줄러가 준비 상태에 있는 프로세스 중 하나를 골라 CPU를 할당하는 작업을 무엇이라고 하는가?
   - CPU 스케줄링
5. 유닉스에서 ctr + z 키를 눌러 프로세스가 중단되면 프로세스는 어떤 상태로 바뀌는가?
   - 휴식 상태
6. 실행 상태에서 하나의 프로세스가 나가고 새로운 프로세스가 들어오는 상황을 무엇이라고 하는가?
   - 문맥 교환(context switching)
7. 실행 중인 프로세스로부터 새로운 프로세스를 복사하는 시스템 호출은 무엇인가?
   - fork()
8. 프로세스의 골격은 그대로 둔 채 코드 영역만 바꾸는 시스템 호출은 무엇인가?
   - exec()
9. 부모 프로세스가 기다리지 않아 자원이 회수되지 못하고 계속 살아있는 프로세스는 무엇인가?
   - 고아 프로세스
10. 프로세스의 코드에 정의된 절차에 따라 CPU에 작업 요청을 하는 실행 단위로서 가벼운 프로세스라고 불리는 것은 무엇인가?
   - 스레드
11. 고아 프로세스를 방지하기 위해 부모 프로세스는 어떤 시스템 호출을 사용하는가?
   - wait()
12. 작업이 끝난 프로세스의 자원을 회수하는 행위를 무엇이라고 하는가?
   - Garbage Collection
13. 모든 프로세스를 부모-자식 관계로 만들어 자원 회수를 용이하게 하는 프로세스의 구조는 무엇인가?
   - 프로세스 계층 구조
