# Integer.MAX_VALUE, Integer.MIN_VALUE
> 최댓값, 최솟값

## 백준 10818번
#백준 

https://www.acmicpc.net/problem/10818

```java
package baekjoon;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class no10818 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt(); // N개의 정수 입력

		List<Integer> arr = new ArrayList<>();

		int min = Integer.MAX_VALUE; // 최소값을 저장할 변수를 초기화
		int max = Integer.MIN_VALUE; // 최대값을 저장할 변수를 초기화

		for (int i = 0; i < N; i++) {
			int num = sc.nextInt(); // N개의 정수를 num으로 입력받음
			arr.add(num);

			// 입력된 정수로 최소값 및 최대값 업데이트
			min = Math.min(min, num);
			max = Math.max(max, num);

		}
		System.out.println(min + " " + max);
	}

}
```
