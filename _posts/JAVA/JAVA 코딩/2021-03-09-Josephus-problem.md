---
title:  "요세푸스 문제" 

categories:
  -  Java Coding
tags:
  - [Programming, JAVA 코딩]

toc: true
toc_sticky: true

date: 2021-03-09
last_modified_at: 
---


<br>

# 요세푸스 문제 프로그래밍

## 🔔  RULE

```
　RULE 1 .
　n 명의 병사들이 동그랗게 서있고, 한 명씩 세어나가면서 매 k 번재 사람이 죽기로 한다 .
　예를 들어 8 명의 병사들이 3명마다 죽이기로 하면 다음 같은 순서로 병사가 죽게 된다 .
　3 ☞ 6 ☞ 1 ☞ 5 ☞ 2 ☞ 8 ☞ 4 ☞ 7

　RULE 2 .
　요세푸스가 살아남기 위해 서 있어야할 자리를 리턴하는 메소드 getSurvivingIndex를 쓰고, ArrayList를 사용하여 구하라 .
```

## 💡 LOGIC

### 살아남는 자리 리턴

```
Info. 
 : number를 받아 ArrayList에 병사를 집어넣는다 .
 : kill 번째 병사 죽이기 .
 : 마지막 생존자 자리 리턴 .
Func. 
 : getSurvivingIndex() - number, kill 을 파라미터로 받아 살아남는 자리를 int형으로 리턴하는 함수 .
```

## 💾 CODE

```java
import java.util.ArrayList;

public class Main {
    public static int getSurvivingIndex(int number, int kill) {

        // number 를 받아 ArrayList 에 병사를 집어넣는다 .
        ArrayList<Integer> soldiers = new ArrayList<>();
        for(int i = 1; i <= number; i++){
            soldiers.add(i);
        }

        // 최후 생존자가 남을 때 까지 반복한다 .
        while(number > 1){

            // kill 번째 자리 이전까지 0번째 자리는 맨 뒤로 이동한다 .
            for(int i = 1; i < kill; i++){
                soldiers.add(soldiers.get(0));
                soldiers.remove(0);
            }

            // kill 번째 병사 죽이기 .
            System.out.println(soldiers.get(0) + "번 군사가 죽습니다 !");
            soldiers.remove(0);
            number--;
        }

        // 마지막 생존자 자리 리턴 .
        return soldiers.get(0);
    }

    public static void main(String[] args) {
        System.out.println("요세푸스는 " + getSurvivingIndex(8, 3) + "번 자리에 서있으면 됩니다.");
    }
}
```

## 💎 RESULT

![image](https://user-images.githubusercontent.com/50429028/110421524-041df080-80e1-11eb-8f9a-87a72ca3a15b.png)

　동그랗게 서있다는 말을 이해하고 적용하는게 가장 힘들었다 ... .

　이렇게 생각하면 이해하기 쉬울듯 하다 .

```
    X
1 2 3 4 5 6 7 8 	// 3 번째 3 kill
4 5 6 7 8 1 2		// 3 번째 6 kill
7 8 1 2 4 5		// 3 번째 1 kill
2 4 5 7 8		// 3 번째 5 kill
7 8 2 4			// 3 번째 2 kill
4 7 8			// 3 번째 8 kill
4 7 4			// 3 번째 4 kill
7
```
<br>

***

개인 기록용 스터디 블로그 입니다.
{: .notice--warning}

[맨 위로 이동하기](#){: .btn .btn--primary }{: .align-right}