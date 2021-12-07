# 설탕 배달(2021/12/07)   

## 문제 : https://www.acmicpc.net/problem/2839   

### 전체적인 흐름

- 5로 나누어 떨어지면 횟수를 세고 반복문을 빠져나옴   
- 5로 나누어 떨어지지 않으면 무게에서 3을 뺌 && 횟수도 셈   
- 위 과정을 무게가 2보다 클 경우에 계속 반복   
- 맨 마지막에 무게가 0 초과 3 미만일 때 횟수를 -1로 반환(3kg짜리로도 5kg짜리로도 해결 안되기 때문)   

```java
package study.sparta.chapter1;

import java.util.Scanner;

public class D_SugarDelivery {
    public static int solution(int kg) {
        int count = 0;
        while (kg > 2) {    // kg >= 3로도 가능
            if (kg % 5 == 0) {
                count += kg / 5;
                break;
            } else {
                kg -= 3;
                count++;
            }
        }
        if (kg < 3 && kg > 0) count = -1;

        return count;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int kg = sc.nextInt();

        System.out.print(solution(kg));
    }
}

```
