---
title: 백준 - step1. 입출력과 사칙연산
categories:
- Java
last_modified_at: 2021-07-01T14:00:00+09:00
toc: true
---
선택언어 java 11 
{: .notice--warning}

## 10171번. 고양이
### :label: 문제
고양이를 출력한다.
{: .notice--info}
```
\    /\
 )  ( ')
(  /  )
 \(__)|
```

### :bookmark: 제출

```java
public class Main {
  public static void main (String[] args){
    System.out.println("\\    /\\");
    System.out.println(" )  ( \')");
    System.out.println("(  /  )");
    System.out.println(" \\(__)|");
  }
}
```


**※ Escape 문자** <br />
**`\\`** : 역슬래시 문자를 출력할때 사용 <br />
**`\"`** : 큰 따옴표를 출력할때 사용 <br />
**`\'`** : 작은 따옴표를 출력할때 사용 <br />

----------------------------------------------------------------------------


## 10172번. 개
### :label: 문제 
개를 출력한다.
{: .notice--info}
```
|\_/|
|q p|   /}
( 0 )"""\
|"^"`    |
||_/=\\__|
```

### :bookmark: 제출

```java
public class Main {
    public static void main(String[] args){
        System.out.println("|\\_/|");
        System.out.println("|q p|   /}");
        System.out.println("( 0 )\"\"\"\\");
        System.out.println("|\"^\"`    |");
        System.out.println("||_/=\\\\__|");
    }
}
```

--------------------------------------------------------------------------

## 1000번. A+B
### :label: 문제 
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.
{: .notice--info}

**> 입력** 
```
1 2
```
**> 출력** 
```
3
```

### :bookmark: 제출
```java
import java.util.*;
public class Main{
	public static void main(String args[]){
		Scanner sc = new Scanner(System.in);
		int a, b;
		a = sc.nextInt();
		b = sc.nextInt();
		System.out.println(a + b);
	}
}
```

--------------------------------------------------------------------------

## 1001번. A-B
### :label: 문제 
<div>
두 정수 A와 B를 입력받은 다음, A-B를 출력하는 프로그램을 작성하시오.
- 입력 : 첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)
- 출력 : 첫째 줄에 A-B를 출력한다.
</div>
{: .notice--info}

**> 입력**
```
3 2
```
**> 출력**
```
1
```

### :bookmark: 제출
```java
import java.util.*;
public class Main{
	public static void main(String args[]){
		Scanner sc = new Scanner(System.in);
		int a, b;
		a = sc.nextInt();
		b = sc.nextInt();
		System.out.print(a-b);
	}
}
```

--------------------------------------------------------------------------

## 10998번. AxB
### :label: 문제
<div>
두 정수 A와 B를 입력받은 다음, AxB를 출력하는 프로그램을 작성하시오.
- 입력 : 첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)
- 출력 : 첫째 줄에 AxB를 출력한다.
</div>
{: .notice--info}

**> 입력** 
```
3 2
```
**> 출력**
```
6
```

### :bookmark: 제출
```java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int a, b;
        a = sc.nextInt();
        b = sc.nextInt();
        System.out.println(a*b);
    }
}
```
--------------------------------------------------------------------------

## 1008번. A/B
### :label: 문제
<div>
두 정수 A와 B를 입력받은 다음, A/B를 출력하는 프로그램을 작성하시오.
- 입력 : 첫째 줄에 A와 B가 주어진다. (0 < A, B < 10)
- 출력 : 첫째 줄에 AxB를 출력한다.실제 정답과 출력값의 절대오차 또는 상대오차가 10-9 이하이면 정답이다.
- (10-9 이하의 오차를 허용한다는 말은 꼭 소수 9번째 자리까지만 출력하라는 뜻이 아니다.)
</div>
{: .notice--info}

**> 입력**
```
1 3
```
**> 출력**
```
0.33333333333333333333333333333333
```
**> 입력** 
```
4 5
```
**> 출력**
```
0.8
```

### :bookmark: 제출
```java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        double a, b;
        a = sc.nextDouble();
        b = sc.nextDouble();
        System.out.println(a/b);
    }
}
```

**참고**
- 상대오차 10^-9이하이면 정답 ? <br />
double을 사용하라는 의미.<br />
float은 10^-7 정도, double은 10^-15정도이다.<br />

--------------------------------------------------------------------------

## 10869번. 사칙연산
### :label: 문제
<div>
두 자연수 A와 B가 주어진다. <br />
이때, A+B, A-B, AxB, A/B(몫), A%B(나머지)를 출력하는 프로그램을 작성하시오. 
- 입력 : 두 자연수 A와 B가 주어진다. (1 ≤ A, B ≤ 10,000)
- 출력 : 첫째 줄에 A+B, 둘째 줄에 A-B, 셋째 줄에 AxB, 넷째 줄에 A/B, 다섯째 줄에 A%B를 출력한다.
</div>
{: .notice--info}

**> 입력**
```
7 3
```
**> 출력**
```
10
4
21
2
1
```

### :bookmark: 제출
```java
import java.util.*;
public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int a, b;
        a = sc.nextInt();
        b = sc.nextInt();
        System.out.println(a+b);
        System.out.println(a-b);
        System.out.println(a*b);
        System.out.println(a/b);
        System.out.println(a%b);
    }
}
```

--------------------------------------------------------------------------

## 10430번. 나머지
- (A+B)%C는 ((A%C) + (B%C))%C 와 같을까?
- (A×B)%C는 ((A%C) × (B%C))%C 와 같을까?

### :label: 문제
<div>
세 수 A, B, C가 주어졌을 때, 위의 네 가지 값을 구하는 프로그램을 작성하시오.
- 입력 : 첫째 줄에 A, B, C가 순서대로 주어진다. (2 ≤ A, B, C ≤ 10000)
- 출력 : 첫째 줄에 (A+B)%C, 둘째 줄에 ((A%C) + (B%C))%C, 셋째 줄에 (A×B)%C, 넷째 줄에 ((A%C) × (B%C))%C를 출력한다.
</div>
{: .notice--info}

**> 입력**
```
5 8 4
```
**> 출력**
```
1
1
0
0
```

### :bookmark: 제출
```java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int a, b, c;
        a = sc.nextInt();
        b = sc.nextInt();
        c = sc.nextInt();
        System.out.println((a+b)%c);
        System.out.println(((a%c)+(b%c))%c);
        System.out.println((a*b)%c);
        System.out.println(((a%c)*(b%c))%c);
    }
}
```

--------------------------------------------------------------------------

## 2588번. 곱셈
### :label: 문제
<div>
(세 자리 수) × (세 자리 수)는 다음과 같은 과정을 통하여 이루어진다. <br />

![image](https://user-images.githubusercontent.com/63999784/124073262-e5bb7680-da7c-11eb-9978-dd05d518dd5a.png)


(1)과 (2)위치에 들어갈 세 자리 자연수가 주어질 때 (3), (4), (5), (6)위치에 들어갈 값을 구하는 프로그램을 작성하시오.

- 입력 : 첫째 줄에 (1)의 위치에 들어갈 세 자리 자연수가, 둘째 줄에 (2)의 위치에 들어갈 세자리 자연수가 주어진다.
- 출력 : 첫째 줄부터 넷째 줄까지 차례대로 (3), (4), (5), (6)에 들어갈 값을 출력한다.
</div>
{: .notice--info}

**> 입력**
```
472
385
```
**> 출력**
```
2360
3776
1416
181720
```

### :bookmark: 제출
```java
import java.util.*;

public class Main {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int a, b;
        a = sc.nextInt();
        b = sc.nextInt();
        int c, d, e;
        c = a*(b%10);
        d = a*((b%100)/10);
        e = a*(b/100);
        System.out.println(c);
        System.out.println(d);
        System.out.println(e);
        System.out.println(c+(d*10)+(e*100));
    }
}
```
