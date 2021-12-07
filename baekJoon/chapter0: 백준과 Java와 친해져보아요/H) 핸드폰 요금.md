# 핸드폰 요금(12/06)

## 문제 : https://www.acmicpc.net/problem/1267

- 사용 시간을 요금제의 초 단위로 나눠 올림을 했다

- 예외처리: 30초(영식 요금제)나 60초(민식 요금제)가 되는 순간 과금된다

```java
package study.sparta.chapter0;

import java.util.Scanner;

public class H_CellPhoneBill {
    public static String solution(int a, int[] input) {
        int sum_youngsik = 0, sum_minsik = 0;

        for(int i : input) {
            if(i % 30 == 0)
                sum_youngsik += Math.ceil((double) i / 30 + 1) * 10;
            else
                sum_youngsik += Math.ceil((double) i / 30) * 10;
            if(i % 60 == 0)
                sum_minsik += Math.ceil((double) i / 60 + 1) * 15;
            else
                sum_minsik += Math.ceil((double) i / 60) * 15;
        }

        if(sum_youngsik < sum_minsik) return "Y " + sum_youngsik;
        else if(sum_youngsik > sum_minsik) return "M " + sum_minsik;
        else return "Y M " + sum_youngsik;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int[] input = new int[a];
        for(int i=0; i<a; i++) {
            input[i] = sc.nextInt();
        }

        System.out.println(solution(a,input));
    }
}
```
