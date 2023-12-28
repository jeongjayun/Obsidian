>[!note] 문자열을 구분해서 사용하고 싶을 때 특정 구분자(Delimter)를 기준으로 나눠서 배열에 담아 이용한다.<br>
>split() 함수의 인수로 구분자가 넘어가며 데이터가 없어도 배열에 담아둔다.

# 사용법
##  public String split(String regex)
- regex : 문자열을 구분하기 위한 정규 표현

### 예제 1 반복문 사용
```java
public class split {  
    public static void main(String[] args) {  
        String str1 = "split 사용방법을 알아봅니다.";  
        String[] words = str1.split("\\s");  
  
        for (String word : words) {  
            System.out.println(word);  
        }  
    }
```

![](https://i.imgur.com/XJkFqLB.png)
<br>
공백을 구분하여 배열에 담은 후 출력한다.

### 예제 2 하나씩 잘라서 배열에 입력
```java
public class split {  
    public static void main(String[] args) {      
        String str2 = "phone;;name;id;pwd";  
        String word1 = str2.split(";")[0];  
        String word2 = str2.split(";")[1];  
        String word3= str2.split(";")[2];  
  
        System.out.println("word1 = " + word1);  
        System.out.println("word2 = " + word2);  
        System.out.println("word3 = " + word3);  
    }  
}
```
![](https://i.imgur.com/2ReIVR0.png)
<br>
for문 돌려 꺼낼 필요 없이 배열에 바로 접근하여 가져올 수 있다. 잘랐는데 내용이 없으면 공백을 반환한다.


## public String split(String regex, int limit)
- limit : 분류할 문자열의 수. 분류할 수 있는 단어가 10개인데 limit가 5이면 5개만 구분하고 나머지는 통으로 출력한다.

### 예제
```java
public class split {  
    public static void main(String[] args) {  
        String str1 = "phone;name;id;pwd";  
        String[] words1 = str1.split(";", 0);  
        String[] words2 = str1.split(";", 2);  
        System.out.println("0일 때 : ");  
        for (String word : words1) {  
            System.out.println(word);  
        }  
  
        System.out.println("\r\n2일 때 : ");  
        for (String word : words2) {  
            System.out.println(word);  
        }  
    }  
}
```

![](https://i.imgur.com/GvbeL9V.png)

# 1018
#코드업 #Java #기초100제 
[[기초-입출력] 시간 입력받아 그대로 출력하기(설명)](https://codeup.kr/problem.php?id=1018)

```java
package codeup;  
  
import java.util.Scanner;  
  
public class no1018 {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
        String str = scanner.nextLine();  
        String[] S = str.split(":");  
        System.out.println(S[0] + ":" + S[1]);  
    }  
}
```