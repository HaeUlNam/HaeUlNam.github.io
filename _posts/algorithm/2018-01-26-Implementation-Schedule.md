---
layout: post
title: 00_1. 왜 자료 구조, 알고리즘을 배워야 할까?
category: 자료구조-알고리즘-구현
permalink: /algorithm/:year/:month/:day/:title/
tags: [DataStructure, Algorithm]
comments: true
---

## 왜 자료 구조, 알고리즘을 배워야 할까?

2학년, 3학년 당시에 자료구조, 알고리즘 과목을 배울 때는 도대체 이걸 배워서 어디다 써 먹어야 하는지 몰랐다.<br>
그래서 이런 것을 누군가 알려주면 좋겠다는 생각을 많이 했었다.<br>
부족하지만, 누군가에게 도움을 될 수 있으면 좋겠다는 맘으로 내 생각을 적어보고자 한다.<br><br>

박트리님의 [알고리즘 공부, 어떻게 해야하나요?](https://baactree.tistory.com/52)에서도 나와있듯이 개발자로서 가장 중요하게 생각하는 것은 <b>배경지식</b>, <b>문제해결능력</b>, <b>구현력</b>이다.<br>

<b>배경지식</b>은 자료 구조, 알고리즘 등을 알고 있는 것. <br>
<b>문제해결능력</b>은 <b>배경지식</b>을 얼마나 적재적소에 적용시킬 것인지, 얼마나 창의적인 시각으로 생각하는 능력.<br>
<b>구현력</b>은 자신의 생각을 코드로 옮기는 능력.<br>

---
하나의 예를 들어보면,
```cpp  
int arr[10] = {0,1,2,3,4,5,6,7,8,9}; 
```
위에서 4를 찾으라고 했을 때, binary search를 모른다면 linear search방식으로<br>
index 0에서부터 찾아나갈 것이다. binary search가 더 효율적인데도 말이다.<br>

물론, 항상 binary search가 linear search방식보다 좋은 것은 아니다. 정렬되어 있지 않는 경우, 정렬을 해야 하기 때문에 binary search가 더 안 좋다고 할 수도 있다.<br>
(binary search와 linear search에 대해서는 나중 포스팅에 다루겠다.)<br><br>

---
여튼, <b>어떻게 구현할 수 있을까? 어떻게 시간을 줄일 수 있을까?</b>과 같이 <b>구현</b>과 <b>튜닝</b>은 항상 개발자에게 존재하는 문제이다.<br>
이런 문제를 해결하는 가장 기초적인 것이 binary search와 같은 <b>배경 지식</b>이라고 생각한다.
<b>배경 지식</b>인 <b>자료 구조 / 알고리즘</b>을 알아야 창의적인 구현도 할 수 있다고 생각한다.

내부적으로 구현된 라이브러리를 잘 쓰는 것도 능력이지만, 무엇보다 더 중요한 것은 내부적으로 어떤 알고리즘으로 구현되었는지 아는 것이다. 현재 학부생 수준에서는 라이브러리가 만능일 수 있지만, 회사에 들어가서 개발을 진행한다면 개발자의 입맛에 맞는대로 라이브러리를 변형 또는 생성할 수 있어야 된다고 생각한다. 거기에서부터 능력 차이가 날 수 있다고 생각한다. 꼭 변형을 하지 않더라도, 전체 프로그램의 복잡도를 알기 위해서는 라이브러리 하나하나가 어떻게 구현되어있는지 알 필요가 있다.<br><br>

컴퓨터공학에는 컴퓨터 구조, 운영체제, 네트워크, 자료 구조, 알고리즘 등 여러 코어 과목들이 있다.<br>
<b>자료 구조, 알고리즘</b>은 코어 과목들 중에도 기초라고 생각한다.<br><br>
따라서, 전산 관련 일은 할려고 하는 사람이라면 기초적인 <b>자료 구조와 알고리즘</b>은 하는 게 맞다고 생각한다.<br><br>
그래서 저 또한 명확하지 않은 <b>자료 구조</b>와 <b>알고리즘</b> 개념을 정리하기 위해 이번 포스팅을 기획하게 되었다.<br>

아래 글들은 내가 포스팅하기 위해, 찾아보면서 insight를 얻은 글이다.<br>
꼭 한번씩 읽어보면 좋겠다.<br>

> 추가적으로 읽으면 좋을 글<br><br>
-임백준님의 [문제는 알고리즘이다](http://m.zdnet.co.kr/column_view.asp?artice_id=20150622080223#imadnews)<br>
-[Why are data structures and algorithms so important in computer science?](https://www.quora.com/Why-are-data-structures-and-algorithms-so-important-in-computer-science)
-네이버랩스 송기선님의 [개발을 잘하고 싶어요](https://www.slideshare.net/mobile/deview/ss-58739254)<br>
-[구글 인터뷰를 보려고 8개월간 풀타임으로 공부한 이유](https://medium.com/@_chyotsuba/%EA%B5%AC%EA%B8%80-%EC%9D%B8%ED%84%B0%EB%B7%B0%EB%A5%BC-%EB%B3%B4%EB%A0%A4%EA%B3%A0-8%EA%B0%9C%EC%9B%94%EA%B0%84-%ED%92%80%ED%83%80%EC%9E%84%EC%9C%BC%EB%A1%9C-%EA%B3%B5%EB%B6%80%ED%95%9C-%EC%9D%B4%EC%9C%A0-d6ce5faff5a7)
-[손코딩 뇌컴파일 눈디버깅](https://brunch.co.kr/@brunch4nrs/2)
<br>
