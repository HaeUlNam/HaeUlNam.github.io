---
layout: post
title: 03/02 BaaaaaaaarkingDog님 코딩테스트 대비 특강
category: 강연
permalink: /lecture/:year/:month/:day/:title/
tags: [lecture, swtest, 삼성 A형]
comments: true
---
<br>

## BaaaaaaaarkingDog님 코딩테스트 대비 특강

### 기초 지식과 자주 실수하는 점

* struct 안에 배열이 있을 경우, 그 안에 배열이 있을 경우 인자로 주면 똑같은 것을 다시 복사한다. (만약, 포인터로 주고 동적배열을 이용하면 주소 값을 전달한다.)

* Vector를 참조자(&)를 사용하지 않고, 전달할 경우 인자로 넘길 떄 O(N)이 걸린다.

* stack overflow를 조심...물론 역량테스트에서는 조심할 필요가 없을 듯하다.

* N 제한으로 알고리즘을 유추할 수 있다.

* visual studio 디버그 모드를 사용하면 어느 줄에서 죽는지 바로 알 수 있다.
    * stl의 경우 어디서 문제가 생기는지 잘 알려주지 않는데, 명령 표시창이 뜨면 무시를 누른 후 스택 프레임을 보면 잘 알 수 있다.

* C2872 Ambiguous sysmbol 같은 경우는 모호한 기호입니다라고 한다.
    * namespace 내에 동일한 변수를 선언했을 때 발생할 수 있는 에러이다.
    * 바킹독님이 말했듯이, 이런 경우가 많았기에 나 같은 경우는 보통 Min과 같이 대문자로 이름을 많이 짓는다.

* 다 풀고 체크할 부분
    * 배열의 크기를 잘 잡았는지
    * 최적화를 더 할 수 없는지
    * testcase를 더 만들어서 확인해보자.

* c++ 98, c++11의 차이
    * 이 때까지 삼성전자는 c++98만을 지원했기에, 아래와 같은 사항을 잘 지키고 코딩해야겠다.
    * {}로 객체를 초기화하는 것은 c++11만 가능하다.
    * c++98에서는 vector< vector < info > >과 같이 >>를 띄어서 써야 한다.

* 시간을 로컬에서 확인할 때는 release 모드로 확인하자.

* 더 디테일한 사항은 [바킹독님 블로그](https://blog.encrypted.gg/category/%EA%B0%95%EC%A2%8C/%EC%8B%A4%EC%A0%84%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)에서 확인해보실 수 있습니다.

---

### 실전 2문제

* [3/2 코딩테스트 대비 모의고사](https://www.acmicpc.net/contest/view/396) 를 풀었습니다.

* 첫번째 문제는 [계란으로 계란치기](https://www.acmicpc.net/problem/16987) 문제입니다. 문제 풀이 초반에 조금 고민하다가, [감시](https://www.acmicpc.net/problem/15683)문제 처럼, 할 수 있는 가짓수를 세고 calulate함수로 마지막에 계산하자는 생각을 했습니다. 여기까지는 좋았는데, 긴장을 했는지 문제의 조건을 빼먹어서 디버깅하는데 시간을 좀 많이 뺐었습니다.. 만약 진짜 삼성 시험에서 이보다 많은 조건들이 나왔다면 수렁에 빠질 수 있겠다라는 생각이 들면서, 아무리 시험 환경에서도 마음을 급하게 먹지 말고 침착하게 문제를 파악하고 설계하는 연습을 더 해야겠다고 생각했습니다.

* 두번째 문제는 [Baaaaaaaaaduk2 (Easy)](https://www.acmicpc.net/problem/16988) 문제입니다. 제 알고리즘 순서는 아래와 같습니다.<br>
    1) map에 주어진 2들을 grouping합니다. <br>
    2) 주어진 map에 모든 경우에 대해 1번 돌을 놓고, 2번 돌을 둘러쌀 수 있는지 계산합니다.<br>
    3) 최대값을 계산.. <br>
    * 여기서 제 문제점은 다음과 같습니다.
        * 처음에 입력을 받으면서 grouping을 하려고 했다. 그런데, 입력 받을 때는 map이 완성되어 있지 않기에 제대로 grouping이 되지 않는 문제가 생긴다.
        * 문제 조건을 제대로 읽지 않아서 size값을 더하지 않고, 단순 덧셈만 진행했다.
        * 2개의 좌표를 재귀로 정하는데, 하나 좌표를 정하고 그 다음 좌표를 계산하는 점이 익숙하지 않아서 시간이 오래 걸렸다.

---

### 문제 풀이

* 바킹독님께서 문제 풀이를 진행해주셨는데, 제가 아는 풀이와 다른 방식도 있어서 너무 흥미로웠습니다. 문제 풀이를 많이 해야 한다고 하셨는데, 바킹독님과 같이 여러 방식으로 바라보는 시각도 동시에 키워야겠다고 생각했습니다.

* 디테일한 문제 풀이에 대해서는 [바킹독님 블로그](https://blog.encrypted.gg/category/%EA%B0%95%EC%A2%8C/%EC%8B%A4%EC%A0%84%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)에서 확인해보실 수 있습니다. 다만, 꼭 실전 2문제를 3시간 맞춰서 풀고 참고하셔서 공부하시면 될 듯 합니다.

---

## 후기

* 문제 퀄리티도 굉장히 좋았고, 이렇게 시험 환경에서 풀어볼 기회가 많이 없는데 좋은 기회를 주셔서 바킹독님께 너무 감사드린다. 1등했다고.. 어묵도 주셔서 너무 맛나게 먹었다.. 이번 강연을 통해 내 문제 문제점을 많이 파악하기도 했지만, 다른 것도 하나 얻었다. 나도 저렇게 나눌 수 있는 사람이 되고 싶다라는 거다. 사실, 이런 문화가 더 깊게 자리 잡을 수록 좋은 개발자.. 좋은 IT 문화가 형성될 듯하다. 자신의 능력을 나누는 것에 대해 다시 한번 더 생각하게 되었고, 피곤하지만 재밌고 행복한 하루였다.