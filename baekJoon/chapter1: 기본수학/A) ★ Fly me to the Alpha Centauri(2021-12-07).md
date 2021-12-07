# Fly me to the Alpha Centauri

## 문제: https://www.acmicpc.net/problem/1011

## 참고 : https://hyunipad.tistory.com/65

### 모르겠다
- 설명을 아무리 찾아서 읽어봐도 모르겠다
- 원리는 이해했다 어떤 규칙인지까지는 이해했는데, 식으로 만드는 과정이 이해가 안된다
- 나중에 다시 보기 위해 별표★를 남긴다

```java
package study.sparta.chapter1;

import java.io.*;

public class A_FlyMeToTheAlphaCentauri {
    public static void main(String[] args) throws NumberFormatException, IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

        int T = Integer.parseInt(br.readLine()); // 테스트 케이스의 개수
        for(int i = 0 ; i < T ; i++) {
            String[] XY = br.readLine().split(" ");
            int x = Integer.parseInt(XY[0]);
            int y = Integer.parseInt(XY[1]);
            int distance = y - x; // 거리
            int max = (int)Math.sqrt(distance); // 최대값(Max)
            if(distance == max * max) { // 1번 경우의 수
                bw.write((max * 2 - 1) + "\n");
            } else if(distance > max * max && distance <= max * max + max) { // 2번 경우의 수
                bw.write(max * 2 + "\n");
            } else { // 3번 경우의 수
                bw.write((max * 2 + 1) + "\n");
            }
        }
        br.close(); bw.flush(); bw.close();
    }
}

```
