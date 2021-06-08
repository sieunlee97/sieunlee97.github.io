---
layout: post
title: 정렬 알고리즘
date: 2021-06-08 16:40:23 +0900
category: Algorithm
---

# 정렬 알고리즘
정렬 알고리즘은 특정 사물이 가진 특성을 기준으로 사물을 순서에 따라서 재배치하는 것으로, 오름차순과 내림차순이 있다. 정렬 알고리즘은 단독으로도 사용되지만, 거의 모든 프로그램에서 공통적으로 사용한다.

## 정렬 알고리즘 종류
1. [버킷 정렬](#버킷-정렬-알고리즘):항목을 조밀한 모집단에서 가져왔다.
2. [기수 정렬](#기수-정렬-알고리즘)
3. [선택 정렬](#선택-정렬-알고리즘)
4. [교환 정렬](#교환-정렬-알고리즘)
5. [삽입 정렬](#삽입-정렬-알고리즘):항목이 몇 개 되지 않는다, 항목이 대부분 정렬되어 있다, 가능한 짧은 코드를 선호한다.
6. [쉘 정렬](#쉘-정렬-알고리즘)
7. [병합 정렬](#병합-정렬-알고리즘)
8. [퀵 정렬](#퀵-정렬-알고리즘):평균 정렬 결과가 필요하다.
9. [힙 정렬](#힙-정렬-알고리즘):최저 상황을 고려해야 한다.


## 버킷 정렬 알고리즘
자료를 버킷이라는 단위 기억 장소에 정렬하고 버킷별 키 값에 따라 다시 정렬하는 알고리즘으로, 사용 방법은 다음과 같다.
![image](https://user-images.githubusercontent.com/63999784/121147858-383db480-c87c-11eb-9301-5656adad9c9d.png)

버킷 정렬은 데이터의 모양에 따른 제한이 있다. 데이터가 1, 1000이면 1000개의 데이터 공간이 필요하다는 문제점이 있다.

## 기수 정렬 알고리즘
버킷 정렬의 문제를 개선하여 만든 것으로, 각 자릿수별로 버킷 정렬을 반복 수행하는 방법이다.
```python
def radix(order) :
  is_sorted = False
  position = 1
  
  while not is_sorted :
     is_sorted = True
     queue_list = [list() for _ in range(10)]
     
     for num in order :
      digit_number = (int) (num/position) % 10
      queue_list[digit_number].append(num)
      if is_sorted and digit_number > 0 :
        is_sorted = False
     index=0
     
     for numbers in queue_list :
      for num in numbers:
        order[index] = num
        index += 1
     position *= 10
     
x=[5,2,8,6,1,9,3,7]
radix(x)
print(x)
```
```java
import static java.lang.System.out;
import java.util.Arrays;

public class RadixSort {
  public static void main (String[] args) {
    int[] array = {12, 326, 127, 467, 110, 58};
    array = rSort(array);
    out.println(Arrays.toString(array));
  }
 
  public static int[] rSort(int[] array) {
    for(int shift = Integer.SIZE-1; shift>-1; shift--){
      int[] tmp = new int[array.length];
      int j = 0;
      for(int i=0; i<array.length; i++){
        boolean move = array[i] << shift >=0;
        if (shift==0? ! move:move) {
          tmp[j] = array[i];
          j++;
        }
        else {
          array[i-j] = array[i];
        }
      }
      for(int i=j; t<tmp.length; i++){
        tmp[i] = array[i-j];
      }
      array = tmp;
    }
    return array;
  }
}

```

## 선택 정렬 알고리즘
