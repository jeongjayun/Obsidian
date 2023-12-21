# Collections.frequency(리스트, 찾고자 하는 값)
> 리스트에서 특정 요소 개수 세기

## 백준 10807번
#백준

https://www.acmicpc.net/problem/10807

```java
package baekjoon;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.List;
import java.util.Scanner;

public class no10807 {
	public static void main(String[] args) {

		// N개의 정수가 주어진다
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();

		// N개의 정수를 입력받아 배열에 추가한다.
		List<Integer> arr = new ArrayList<>();

		for (int i = 0; i < N; i++) {
			int a = sc.nextInt();
			arr.add(a);
		}

		// 찾으려는 숫자 v
		int v = sc.nextInt();

		int result = Collections.frequency(arr, v);
		System.out.println(result);

	}

}
```