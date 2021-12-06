# 달팽이는 올라가고 싶다

## 문제: https://www.acmicpc.net/problem/2869   

### 1. 동작은 되지만 런타임에러
- for문 때문인 것 같음
```java
package study.sparta.chapter1;

import java.util.Scanner;

public class B_SnailsWantsToGoUp {
    //런타임에러
    public static int solution(int a, int b, int v) {
        int sum = 0;
        for(int i=1; i<=v; i++) {
            if(sum+a >= v) return i;
            else if(sum+(a-b) >= v) return i;
            else sum+=(a-b);
        }
        return 0;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        int v = sc.nextInt();

        System.out.println(solution(a,b,v));
    }
}

```
