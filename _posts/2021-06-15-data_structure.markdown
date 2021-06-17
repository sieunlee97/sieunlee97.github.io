---
layout: post
title: 자료구조
date: 2021-06-15 16:40:23 +0900
category: Data_Structure
---

# 컴퓨터 자료형

| 기본 자료형 	| 사용자정의 자료형                                    	|
|-------------	|------------------------------------------------------	|
| 숫자        	| **배열** : 동일한 자료형을 여러개 모은 것            	|
| 문자        	| **구조체** : 동일하거나 다른 자료형을 여러개 모은 것 	|
| 논리값(T/F) 	| **클래스** : 구조체에 메소드(함수)까지 포함한 것     	|
|             	| **재정의 자료형**                                    	|

# 자료구조
물리적 구조에 따라 리스트/연결리스트로 나뉜다.
- 리스트(List) : 각 데이터를 연이어 저장하는 기술
- 연결리스트(Linked List) : 각 데이터를 임의의 위치에 저장하고 서로를 연결하는 기술

## 리스트형 자료구조
연속적인 저장 형태
- 배열 : 크기가 변하지 않는 리스트형 자료구조, 중간값을 지워도 빈칸으로 유지
- 리스트 : 크기가 변하는 자료구조, 중간값 지우면 뒤의 값이 앞으로 이동

## 연결 리스트 자료구조
저장하는 각 데이터가 데이터 외에 다음과 이전의 데이터를 가리키는 정보를 갖는 구조
- 연결리스트 : (데이터)+(다음데이터 포인터), 한방향 탐색
- 더블연결리스트 : (이전 데이터 포인터)+(데이터)+(다음 데이터 포인터), 양방향 탐색
- 환형연결리스트 : 더블연결리스트의 양 끝 연결

### 연결 리스트를 이용한 스택 구현
- 스택 : 나중에 들어온 데이터가 가장 먼저 사용되는 자료구조

Link.java

```java

/*
Link를 구성하는 클래스
*/
public class Link {
    public int data1;
    public double data2;
    public Link nextLink; //다음 링크
    
    // Link 생성자
    public Link(int d1, double d2) {
        data1 = d1;
        data2 = d2;
    }
    
    // Link 데이터 출력
    public void printLink() {
        System.out.print("{"+data1+","+data2+"}");
    }
}

```


LinkList.java

```java
/*
연결 리스트를 실제 구현하는 클래스
*/
public class LinkList {
    
    private Link first; // 첫번째 링크 = top
    
    // LinkList 생성자
    public LinkList(){
        first = null; //변수 초기화
    }
    
    public boolean isEmpty(){ // 비어있다면
        return first == null; //첫번째 링크 null
    }
    
    // 데이터 추가
    public void insert(int d1, double d2){
        Link link = new Link(d1,d2);
        link.nextLink = first; //다음 링크에 첫번째 링크 값 넣음 
        first = link; // 첫번째 링크에 새로 추가한 링크 값 넣음 = top
    }
    
    // 데이터 삭제
    public Link delete(){
        Link temp = first; // temp에 첫번쨰 링크값(삭제할값) 넣음
        first = first.nextLink; // 첫번쨰 링크에 다음 링크값 넣음
        return temp; 
    }
    
    public void printList() {
        Link currentLink = first; // 현재 링크에 첫번째 링크값 넣음
        System.out.print("List : ");
        while(currentLink != null){ // 현재 링크가 null이 아니라면 반복 = null이 될때까지 반복
            currentLink.printLink(); // 출력
            currentLink = currentLink.nextLink; //그런다음, 현재 링크에 다음 링크 넣음
        }
        System.out.println("");
    }
}

```

LinkListTest.java
```java
/*
연결리스트를 실제 사용하는 
*/
class LinkListTest {
    public static void main (String args[]){
        LinkList list = new LinkList();
        list.insert(1, 100);
        list.insert(2, 200);
        list.insert(3, 300);
        list.insert(4, 400);
        list.insert(5, 500); //시작 - first 링크
        
        list.printList();
        
        while(!list.isEmpty()){
            Link deletedLink = list.delete();
            System.out.print("deleted : ");
            deletedLink.printLink();
            System.out.println("");
        }
        list.printList();
    }
}
```

## 해쉬 테이블의 구현

해쉬테이블은 데이터를 저장할 때, 저장할 위치를 해쉬 함수를 이용해서 생성하고, 생성된 위치에 데이터를 저장하는 방식에서 사용하는 주소 테이블이다. 순서 리스트와 연결 리스트 자료구조를 조합하여 사용하며, 데이터에 직접적인 접군이 가능하여 저장 및 읽기 속도가 빠르다. 데이터베이스에서 데이터를 저장할 때 주로 사용한다.

![image](https://user-images.githubusercontent.com/63999784/122387826-39708f00-cfaa-11eb-936a-f68dc138feaa.png)

1. 데이터를 저장할 때, 각 데이터마다 해쉬 함수를 돌리면 배열 항목이 나오게 된다.
2. '이시은'을 해쉬 함수로 돌리면 0이 나오므로 '이시은'은 배열의 0번지에 저장된다.
3. '00대'를 해쉬 함수로 돌렸을 때 2가 나오면 배열의 2번지에 저장한다.
4. '00시'를 해쉬 함수로 돌렸을 때 2가 나오면 배열의 2번지에 저장해야 하는데, 이미 '00대'가 있으므로 '00대'와 '00시'는 연결 리스트로 연결한다.

