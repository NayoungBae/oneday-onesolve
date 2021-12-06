# ACM 호텔

## 문제 : https://www.acmicpc.net/problem/10250

### 틀렸습니다: 어디가 잘못 되어있는 지 모르겠음..

```java
package study.sparta.chapter1;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class C_ACMHotel {
    //그냥 틀렸다는데?
    public static List<Integer> solution(int a, String[] input) {
        List<Integer> answer = new ArrayList<>();
        for(int i=0; i<a; i++) {
            int height = Integer.parseInt(input[i].split(" ")[0]);
            int width = Integer.parseInt(input[i].split(" ")[1]);
            int num = Integer.parseInt(input[i].split(" ")[2]);

            //000부터 시작이 아닌 101부터 시작해야함
            int x = 1, y = 1;
            int px = num % height;
            double divide = (double) num / height;  //몫을 구하는 것이 아닌 소수점까지 나오는 나눗셈
            int py = (int) Math.ceil(divide);

            int result = 0;

            if(px == 0) result = py * 100 + height;
            else {
                int rx = x + (px - 1);
                int ry = y + (py - 1);
                result = rx*100 + ry;
            }
            answer.add(result);
        }
        return answer;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = Integer.parseInt(sc.nextLine());
        String[] input = new String[a];
        for(int i=0; i<a; i++) {
            input[i] = sc.nextLine();
        }

        for(Integer i: solution(a,input)) {
            System.out.print(i + " ");
        }
    }
}

```

---

### 정답입니다

```java
package study.sparta.chapter1;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class C_ACMHotel {
    public static List<Integer> solution(int a, String[] input) {
        List<Integer> answer = new ArrayList<>();
        for(int i=0; i<a; i++) {
            int height = Integer.parseInt(input[i].split(" ")[0]);
            int width = Integer.parseInt(input[i].split(" ")[1]);
            int num = Integer.parseInt(input[i].split(" ")[2]);
            int floor = num % height, room = num / height + 1;
            if (num % height == 0) {
                room = num / height;
                floor = height;
            }
            answer.add(floor * 100 + room);
        }
        return answer;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = Integer.parseInt(sc.nextLine());
        String[] input = new String[a];
        for(int i=0; i<a; i++) {
            input[i] = sc.nextLine();
        }

        for(Integer i: solution(a,input)) {
            System.out.print(i + " ");
        }
    }
}
```
