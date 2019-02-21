---
layout: post
title: 06. 퀵 소트(QuickSort) & Randomized QuickSort
category: 자료구조-알고리즘-구현
permalink: /algorithm/:year/:month/:day/:title/
tags: [DataStructure, Algorithm, Sort, QuickSort, nlogn, Randomized]
comments: true
---
<br><br>
* 시작하기에 앞서 이번 포스팅은 광운대학교 황호영 교수님의 알고리즘 수업을 참고하여 만들어졌습니다. 아래의 모든 그림은 Introduction to Algorithm ppt에서 가져왔습니다.

---

## Quick Sort Intro

* Quick이라는 말 그대로 Sort 중에 빠른 축에 속하는 알고리즘이다. <br> 평균적으로 nlogn이긴 하지만, pivot을 결정할 때 Skewed data (치우친 데이터)가 있을 수 있기에, 그냥 Quick Sort는 최악의 경우 n제곱이다.

* QuickSort를 튜닝하여 사용하면, 최악의 경우에도 nlogn을 유지할 수 있다.

* 따라서 먼저 QuickSort 알고리즘을 설명하고, Randomized Quick Sort를 왜 써야 하고, 어떻게 사용할지 설명하겠다.

---

## Quick Sort 개념 설명

* 퀵 소트는 Divide & Conquer를 적용한 알고리즘이다.
    * 따라서, 오른쪽과 같이 3가지 기능이 존재한다. Divide, Conquer, Combine


* 보통 QuickSort에서는 pivot을 가장 왼쪽에 있는 것으로 선택한다. pivot을 중심으로 왼쪽과 오른쪽을 나누기 위해, i와 j를 각각 start, start + 1로 초기화한다. 그리고 j가 end를 넘어갈 때까지 진행한다. 마지막으로 i와 pivot의 자리를 바꾸고 왼쪽 오른쪽 부분을 재귀적으로 수행한다.

<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_0.png"/> 
</center><br>

아래의 예제를 천천히 따라가보며, QuickSort를 이해해보자.

<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_1.png"/> 
</center><br>
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_2.png"/> 
</center><br>

pivot = 1 / i = 1 / j = 2일 때, arr[j]는 arr[pivot]보다 크기 때문에, j <- j + 1 만 해주고 다음으로 넘어간다.

 
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_3.png"/> 
</center><br>

1번과 동일하게 j<- j+1
 
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_4.png"/> 
</center><br>

j번째의 수가 pivot보다 작기에, i <- i + 1을 한 뒤 arr[i]와 arr[j]의 수를 swap한다.

<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_5.png"/> 
</center><br>

<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_6.png"/> 
</center><br>
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_7.png"/> 
</center><br>
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_8.png"/> 
</center><br>
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_9.png"/> 
</center><br>
<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_10.png"/> 
</center><br>

<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_11.png"/> 
</center><br>

<center>
        <img style="max-width: 60%; height: auto;" src="/assets/post-img/algorithm/quicksort_12.png"/> 
</center><br>

반복적으로 수행하다가, 마지막에 pivot을 자신의 위치로 두고 재귀적으로 왼쪽 오른쪽을 반복적으로 수행하면 된다.

---

## Quick Sort 시간복잡도

* worst case는 정렬되어있는 경우인데, quicksort 적용 시에 오른쪽으로 데이터들이 skewed되어 있기에 n제곱의 시간이 걸린다.

* 비교 횟수로 시간복잡도를 계산해보면, 아래와 같다.

* n + n-1 + n-2 + n-3 .... + 1 = n(n+1)/2이기에, 시간복잡도로는 n 제곱이다.

* worst case 예시 <br>
    1 2 3 4 5 6 7 

---
## Randomized Quick Sort

* Radomzied Quick Sort는 원래 Quick Sort의 worst case를 nlogn으로 만들고자 튜닝하여 사용하는 방식이다.

* 아래와 같이 random으로 pivot을 고르는 함수를 만들고, 고른 pivot을 return하여 start지점의 값과 변경하는 방식으로 진행했다.

```cpp  
int randomPivot(int start, int end)
{
    int diff = end - start;
    int randomNum = rand() % (diff + 1);

    return start + randomNum;
    //start와 end 값의 사이 값을 rand함수로 고르고, 이를 start와 더해서 최종 index를 결정한다. 
}
```
```cpp
int pivotidx = randomPivot(start, end);
swap(arr[start], arr[pivotidx]);
pivotidx = start;
```

* 사실, Random적으로 pivot을 고르면 왜 더 줄어드는지는 수학적으로 증명은 어렵지만 아래와 같이 이해한 것을 설명하겠다.<br>
-> 지금 이해한 것으로는 Quick Sort는 한 번 skewed data가 생길 경우, 재귀적으로 skewed data에 대해 수행해야한다. 하지만 randomized 방식을 사용하면 한번 skewed data가 발생하였다고 해도, 그 다음은 rand으로 pivot을 결정할 때 또 1/n의 확률로 결정되기에 skewed한 상황이 지속적으로 일어나지 않는다. 따라서, randomized Quick Sort가 점근적으로 nlogn에 접근한다고 할 수 있다. 

* [위키피디아 - 확률적 알고리즘](https://ko.wikipedia.org/wiki/%ED%99%95%EB%A5%A0%EC%A0%81_%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98) 을 참고해도 좋을 듯합니다.

---

## 장점

* Inplace sort이기에 메모리가 상대적으로 적게 필요하다.
    * 할당된 배열 하나로 정렬을 진행할 수 있다는 뜻이다.

* Locality of reference가 좋다.
    * [Does partition function gives quick sort its locality of reference?
](https://stackoverflow.com/questions/30867112/does-partition-function-gives-quick-sort-its-locality-of-reference) 참고하자.

---

## 단점

* 데이터가 클 경우, Disk Head overhead가 클 수 밖에 없다. 그래서 bucket으로 일정 범위를 나누어 quicksort를 돌리는 것이 효율적이다.

* Unstable
    * 3 4' 2 1 4 이렇게 같은 수의 데이터가 들어왔을 때, 4과 4'의 순서가 보장되지 않는 것이 unstable한 것인데, 보장되지 않는다. 

---

## 추천하는 알고리즘 문제

[2751번: 수 정렬하기 2](https://www.acmicpc.net/problem/2751)를 통해서 Quick Sort를 작성하여 한번 돌려보고, Randomized Quick Sort를 적용하여 돌려보는 것을 추천한다.

---

## 코드

https://github.com/HaeUlNam/Algorithm/tree/master/DataStructure_Algorithm_implementation/Sorting/QuickSort 

---

* 질문은 언제나 환영입니다! 댓글이나 메일로 보내주세요!!