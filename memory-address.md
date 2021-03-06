---
title:  "메모리 주소"

categories:
  - IT
tags:
  - [memory]
toc: true
toc_sticky: true
---

## 메모리 주소

Windows 운영체제의 x86(32비트) 또는 x64(64비트)라는 것은 직관적으로 말하자면 데이터 처리 단위라고 할 수 있습니다.

32개의 비트가 있다는 것은 2^32의 경우의 수를 갖고,

64개의 비트가 있다는 것은 2^64의 경우의 수를 갖는다는 것이죠.

**2^32 = 4,294,967,296 (약 43억)**

**2^64 = 18,446,744,073,709,551,616 (약 1844경)**



**메모리 한칸은 `1byte`의 크기**를 갖고 있습니다. 그리고 **32bit 운영체제**에서는 32개의 비트, 즉 **4바이트 길이의 주소**를 갖습니다. 쉽게 말하자면 집 평수는 1평이고, 이 집을 가리키는 주소는 32자리로 표현된다고 보시면 됩니다.

그리고 2^32까지의 경우의 수가 있으니, 4,294,967,296 개의 주소를 가리킬 수 있다는 의미이고, 이는 1바이트 크기의 메모리가 4,294,967,296 개 까지 인식이 가능하다는 것, 즉 메모리의 최대 크기는 **4,294,967,296 byte = 4GB** 입니다.

그럼 64bit 는 8바이트이므로 하나의 주소가 **8바이트 길이의 주소**를 갖는다는 것을 알 수 있습니다. 즉, 18,446,744,073,709,551,616 개의 주소를 가리킬 수 있다는 의미고, 이는 18,446,744,073,709,551,616 byte = 16EB(엑사바이트) = **16384TB**(테라바이트) 까지 입니다. 한 마디로 이론적으로는 램을 16EB까지 설치 할 수 있다는 것이죠.

통상적으로 편의상 16진수로 나타내면,

32bit에서는 0x00000000 ~ 0xFFFFFFFF

64bit에서는 0x0000000000000000 ~ 0xFFFFFFFFFFFFFFFF

![memory-size](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FmQaS1%2FbtqUYfomQwa%2FHY44kytEk9DJB8vAmbRDpK%2Fimg.png)



즉, 64비트 운영체제는 메모리 한 칸의 주소를 64비트로 표현하며 이는 8바이트와 같은 의미이고, 메모리 주소를 8바이트로 표현하기 때문에 포인터(주소를 가리키는 변수)의 크기 또한 8바이트입니다.



![C-memory](https://img1.daumcdn.net/thumb/R1920x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FduuWma%2FbtqU0zgyW7v%2FOMzKAW1G6xZeczPcDSR3J1%2Fimg.png)

C 언어로 작성된 프로그램을 예시로 살펴보면 

**상수, 함수**는 **Text 영역**에

**전역, 정적변수**는 **Data 영역**에

**동적할당**이 되는 변수들은 **Heap영역**에  (malloc 함수 : 런타임(실행중)에 메모리를 동적으로 할당할 수 있는 함수)

**지역변수**들은 **Stack 영역**에 위치하게 됩니다.

쉽게 생각하면 위 4개의 영역 중 Text영역이 가장 낮은 주소(0에 가까운 주소), Data영역이 그 다음 주소, Heap영역이 Data영역의 다음 주소, Stack영역은 4개 영역 중 가장 높은 주소에 위치한다고 보면 되죠.



출처 - [https://st-lab.tistory.com/198?category=872072](https://st-lab.tistory.com/198?category=872072)