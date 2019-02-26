---
layout: post
title: 08. 다음 순열(Next Permutation)
category: 자료구조-알고리즘-구현
permalink: /algorithm/:year/:month/:day/:title/
tags: [DataStructure, Algorithm, Permutation, Next_Permutation, 조합]
comments: true
---
<br><br>

---
## 다음 순열

```cpp  
#include<algorithm>
#include<vector>

vector<int> a = {1,2,3};
next_permutation(a.begin(), a.end());

//위와 같이 하면 1,3,2가 a에 저장된다.
```

---

## 순열의 끝인지 확인 방법

1. 위처럼 vector가 있으면 정렬하여서, next_permutation한 것과 비교하면 된다.

    ```cpp  
    #include<algorithm>
    #include<vector>

    vector<int> a = {1,2,3};
    vector<int> com = a;

    sort(com.begin(), com.end());
    next_permutation(a.begin(), a.end());

    int check = false;
    for(int i = 0; i < a.size(); i++)
    {
        if(a[i] != com[i])
        {
            check = true;
            break;
        }
    }

    if(!check)
    {
        cout << "The End Permutation" << endl;
    }
    ```

2. 사실 next_permutation()에서 return값이 false이면, 다음 순열이 없는 것이다.

    ```cpp
    if(!next_permutation(a.begin(), a.end()))
    {
        cout << "The End Permutation" << endl;
    }
    ```
---

## 라이브러리 사용 안하려면..

https://kwanghyuk.tistory.com/25 여기 확인해서 공부해보자..