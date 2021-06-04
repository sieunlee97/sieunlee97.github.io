---
layout: post
title: 다형성
date: 2021-06-04 18:30:23 +0900
category: Spring
---

# 다형성 이용하기

**결합도를 낮추기 위한 방법** 중 가장 쉽게 생각할 수 있는 것이 다형성을 이용하는 것이다.<br>
다형성을 이용하려면 **상속과 메소드 재정의(Overriding), 형변환**이 필요하며, 자바 같은 객체지향 언어는 이를 문법으로 지원한다.

  ### 다형성 이용하지 않은 예시 (아래)

![image](https://user-images.githubusercontent.com/63999784/120777347-26989c00-c560-11eb-94d3-11fee5bf08c0.png)
![image](https://user-images.githubusercontent.com/63999784/120777435-3dd78980-c560-11eb-81a8-518a352f2220.png)

위와 같은 방식으로 하면, SamsungTV와 LgTV 클래스는 같은 기능을 수행하는 메소드가 있지만, 메소드 이름이 서로 다르다.<br>
이 두 TV클래스를 번갈아 사용하는 TVUser 프로그램을 구현하면, 아래와 같다.

![image](https://user-images.githubusercontent.com/63999784/120777647-79725380-c560-11eb-9736-106400d73077.png)

SamsungTV와 LgTV는 메소드 시그니처가 다르므로 TVUser 코드 대부분을 수정해야 TV를 교체할 수 있다.<br>
현재 상태에서는 두 TV클래스가 같은 메소드를 가지게끔 강제할 수 있는 수단이 없다. TVUser와 같은 클라이언트 프로그램이 하나가 아니라 여러개라면 유지보수는 더 힘들 것이다.


  ### 다형성 이용한 예시(아래)
TV 클래스들의 최상위 부모로 사용할 TV인터페이스 추가하고, 모든 TV가 공통으로 가져야 할 메소드를 추상메소드로 선언한다.

#### TV.java
```java
package com.springbook.biz;

public interface TV {
	public void powerOn();
	public void powerDown();
	public void volumeUp();
	public void volumeDown();
}
```

SamsungTV.java와 LgTV.java 클래스를 수정하여 방금 추가한 TV인터페이스를 구현하도록 한다.
#### SamsungTV.java
```java
package com.springbook.biz;

public class SamsungTV implements TV {
	@Override
	public void powerOn() {
		System.out.println("SamsungTV----전원 켠다.");
	}
	@Override
	public void powerOff() {
		System.out.println("SamsungTV----전원 끈다.");
	}
	@Override
	public void volumeUp() {
		System.out.println("SamsungTV----소리 올린다.");
	}
	@Override
	public void volumeDown() {
		System.out.println("SamsungTV----소리 내린다.");		
	}
}
```
#### LgTV.java
```java
package com.springbook.biz;

public class LgTV implements TV {
	@Override
	public void powerOn() {
		System.out.println("LgTV----전원 켠다.");
	}
	@Override
	public void powerOff() {
		System.out.println("LgTV----전원 끈다.");
	}
	@Override
	public void volumeUp() {
		System.out.println("LgTV----소리 올린다.");	
	}
	@Override
	public void volumeDown() {
		System.out.println("LgTV----소리 내린다.");	
	}
}
```

결국, 인터페이스를 이용하여 모든 TV 클래스가 같은 메소드를 가질 수 밖에 없도록 강제할 수 있게 되었다.<br>
이제 TVUser.java에서 두 TV를 이용해보자.

#### TVUser.java
```java
package com.springbook.biz;

public class TVUser {

	public static void main(String[] args) {
		TV tv = new SamsungTV();
		tv.powerOn();
		tv.volumeUp();
		tv.volumeDown();
		tv.powerOff();
	}
}
```
LgTV로 교체하고 싶다면, 팜조하는 객체만 SamsungTV에서 LgTV로 교체해주면 된다.<br>
이렇게 다형성을 이용하면 TVUser와 같은 클라이언트 프로그램이 여러 개 있더라도 최소한의 수정으로 유지보수 할 수 있다.
