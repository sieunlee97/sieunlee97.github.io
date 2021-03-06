---
layout: post
title: 알고리즘이란
date: 2021-06-02 19:20:23 +0900
category: Algorithm
---

# Algorithm
주어진 문제를 해결하기 위한 절차로서, 정해진 입력에 정해진 출력이 나와야하고, 무한히 반복되어서는 안된다.<br>
주어진 문제를 단위 작업으로 나누고 문제를 해결하기 위한 처리 순서를 정하는 과정<br><br>
ex) 수강 신청하는 프로그램 개발<br>
**단위작업으로 분리(programming)**
- 입력받을 데이터 타입을 정하고 선언
- 입력받을 화면 보여주고, 사용자 입력받기
- 입력받은 데이터를 DB에 저장하기
- 사용자가 선택할 수 있는 메뉴 보여주기
- 사용자가 로그인하기

**분리된 작업을 수강 신청이 되도록 순서대로 정렬하기(algorithm)**
- 사용자가 로그인하기
- 메뉴 보여주기
- 선택한 메뉴에 대한 화면 보여주기
- 사용자의 입력 받기
- 입력받은 데이터를 DB에 저장하기

**각 단위 작업을 컴퓨터 언어로 전환하기(coding)**

### 알고리즘의 종류
1. **정렬(Sort)** : 한 줄로 모여 있는 데이터를 오름차순이나 내림차순으로 배치하는 방법
    - 단순정렬 알고리즘, 선택정렬 알고리즘, 쉘 정렬 알고리즘, 퀵 정렬 알고리즘..
3. **검색(Search)** : 데이터 중에서 원하는 것을 찾아내는 방법
    - 순차검색 알고르짐, 이진검색 알고리즘..
5. **문자열 패턴 매칭(SPM : String Pattern Matching)** : 주어진 문자열에서 지정한 문자열과 일치하는 부분을 찾아내는 방법
    - 문자열 검색 알고리즘, KMP 검색 알고리즘, BM 검색 알고리즘..
7. **계산(Carculation)** : 수학이나 공학의 문제 해결을 위한 방법
    - 데이크스트라 알고리즘(최단 경로 찾기), 가우스 소거법(방정식 풀기)..

### 알고리즘의 표현
다양한 방식으로 표현할 수 있지만, 가장 많이 사용되는 방법은 **흐름도(Flow Chart)** 를 사용하는 것이다.

![flow chart](https://user-images.githubusercontent.com/63999784/120423316-243e1280-c3a5-11eb-9174-f94218a87269.PNG)

ex) (위) 두 개의 수를 입력받고 큰 값을 출력하는 알고리즘

<br>
> 참고 : 그림으로 정리한 알고리즘과 자료구조 - 조민호
