---
layout: post
title: 0. 포스팅 소개_1 (이유)
category: 자료구조-알고리즘-구현
permalink: /algorithm/:year/:month/:day/:title/
tags: [DataStructure, Algorithm]
comments: true
---

## 왜 자료 구조, 알고리즘을 배워야 할까?

2학년, 3학년 당시에 자료구조, 알고리즘을 배울 때는 도대체 이걸 배워서 어디다 써 먹어야 하는지 몰랐다.<br>
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

내부적으로 구현된 라이브러리를 잘 쓰는 것도 능력이지만, 무엇보다 더 중요한 것은 내부적으로 어떤 알고리즘으로 구현되었는지 아는 것이다. 현재 학부생 수준에서는 라이브러리가 만능일 수 있지만, 회사에 들어가서 개발을 진행한다면 개발자의 입맛에 맞는대로 라이브러리를 변형 또는 생성할 수 있어야 된다고 생각한다. 거기에서부터 능력 차이가 날 수 있다고 생각한다.<br><br>
컴퓨터공학에는 컴퓨터 구조, 운영체제, 네트워크, 자료 구조, 알고리즘 등 여러 코어 과목들이 있다.<br>
<b>자료 구조, 알고리즘</b>은 코어 과목들 중에도 기초라고 생각한다.<br><br>
따라서, 전산 관련 일은 할려고 하는 사람이라면 기초적인 <b>자료 구조와 알고리즘</b>은 하는 게 맞다고 생각한다.<br><br>
그래서 저 또한 명확하지 않은 <b>자료 구조</b>와 <b>알고리즘</b> 개념을 정리하기 위해 이번 포스팅을 기획하게 되었다.<br>

> 추가적으로 읽으면 좋을 글<br><br>
임백준님의 [문제는 알고리즘이다](http://m.zdnet.co.kr/column_view.asp?artice_id=20150622080223#imadnews)<br>
[Why are data structures and algorithms so important in computer science?](https://www.quora.com/Why-are-data-structures-and-algorithms-so-important-in-computer-science)

<br>

## 알고리즘이 취업에는 얼마나 중요할까?

이어서 알고리즘이 취업에는 얼마나 도움이 될까를 조사해보려고 한다.<br>
대부분의 IT기업들은 알고리즘 테스트를 통해, 신입을 채용하고자 한다.<br>

1. 삼성전자 및 삼성SDS<br>
<img src="/assets/post_img/삼성SDS_채용전형.png"/> <br>
2. 카카오<br>
<img src="/assets/post_img/카카오_채용전형.png"/> <br>
3. SK하이닉스 <br>
<img src="/assets/post_img/sk하이닉스_채용전형.png"/> <br>
4. 현대자동차 <br>
<img src="/assets/post_img/현대자동차_채용전형.png"/> <br>
5. LINE <br>
<img src="/assets/post_img/라인_채용전형.png"/> <br>

각 회사별 수준 차이는 많이 나고 유형도 다르기에 그에 맞추어 잘 준비해도 좋을 듯하다. <br>
sk하이닉스는 skct 인적성도 같이 본다고 한다. <br><br>


## 알고리즘 대회 및 대외활동

- 추가적으로 알고리즘 대회들이 어떤 것이 있는지 알아보자.

1. [Google CodeJam](https://codingcompetitions.withgoogle.com/codejam)<br>
구글에서 개최하는 알고리즘 대회로서, 우수한 성적만 거둔다면 구글 입사! <br>
3~4월부터 시작해서, 8월 정도에 끝나는데 Round 1,2,3 Final까지 총 4단계로 이루어져 있고, 단계를 올라 갈수록 사람을 줄여나간다. <br>
-> 참고할만한 자료: [Google Code Jam 참가 후기](https://blog.outsider.ne.kr/784)

2. [Facebook Hacker Cup](https://www.facebook.com/hackercup/)<br>
코드 잼과 비슷한 방식으로 하고, 6월에 진행된다고 한다.

3. [삼성전자 대학생 프로그래밍 경진대회(SCPC)](https://news.samsung.com/kr/%EC%82%BC%EC%84%B1%EC%A0%84%EC%9E%90-%EC%A0%9C-4%ED%9A%8C-%EB%8C%80%ED%95%99%EC%83%9D-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EA%B2%BD%EC%A7%84%EB%8C%80%ED%9A%8C-%EC%B0%B8)<br>
6월, 7월에 열리는 대회로서 본선 대회에 입상한다면, [삼성 소프트웨어 멤버십](http://secmem.org/)에 가입가능하다고 한다.<br>

4. [카카오 코드 페스티벌](https://www.kakaocode.com/)<br>
8월 정도에 열리는 대회로서 본선 대회에 입상하면, 카카오 신입 코딩 테스트 면제와 우수 성적자는 인턴의 기회가 부여된다고 한다.<br>

5. [ACM ICPC](http://icpckorea.org/)<br>
10월 정도에 열리는 대회로서 3명이 팀을 이루어 문제를 시간 안에 푼다.<br>
문제는 영어로 나오게 되고, 문제를 푸는 것 뿐만 아니라 팀 워크도 중요하다고 할 수 있는 대회이다.

6. [Codeforce](https://codeforces.com/)<br>
코드 포스는 주기적으로 계속 대회가 열리고, 푼 문제에 따라 점수도 오르는 방식이다.<br>
실력을 쌓는데, 좋은 곳이라고 생각된다.

7. [Backjoon 대회 사이트](https://www.acmicpc.net/contest/official/list)<br>
UCPC, 각 대학교별 알고리즘 대회 등등에 참여할 수 있도록 이루어져 있다.<br>
이런 알고리즘 대회도 해보는 것 좋을 듯하다.<br><br>

끝으로 누구든지 노력한다면, 대회에서 입상할 수 있다고 생각한다.<br>
물론.... 나도 입상해보고 싶다...