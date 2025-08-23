---

표준 라이브러리 클래스를 불러오기 위한 import문 : 

import.java.lang.Math

→ 하지만, 컴파일 시 자동으로 불러오기 때문에 굳이 따로 선언할 필요가 없다.


<br><br>
### 1. Math.abs()
- 절댓값으로 반환해준다.

예시 :
```java
public class Sample {
    public static void main(String[] args) {
        System.out.println(Math.abs(-1)); // 1
        System.out.println(Math.abs(0)); // 0
        System.out.println(Math.abs(1)); // 1
    }
}
```
→ 전부 **절댓값**으로 반환된다.


<br><br>
### 2. Math.random()
- 0.0~1.0사의의 값을 double형인 랜덤값으로 반환한다.

예시 :

Math.random();

→ ex) 0.8154…

이것을 응용하여 특정 수의 범위를 만들 수 있다.

예시 :

```java
public class Sample {
    public static void main(String[] args) {
        System.out.println((int) (Math.random() * 10)); // 0~9
        System.out.println((int) (Math.random() * 100)); // 0~99
        System.out.println((int) (Math.random() * 1000)); // 0~999
    }
}
```
원리 : 0.0에서 1.0사이의 값이 나온다고 했으므로 예를들어 0.8145….값이 나왔다고 가정해보자.

그러면 0.8145 * 10 = 8.145….가 된다. 여기서 강제로 int형으로 변환하면 8만 남게되므로 내가 원하는 0~9사이의 난수가 된다.


<br><br>
### 3. Math.round(), Math.floor(), Math.ceil()

반올림 : Math.round()

내림 : Math.floor()

올림 : Math.ceil()

예시 : 
```java
public class Sample {
    public static void main(String[] args) {
        System.out.println(Math.round(5.5341)); // 6
        System.out.println((int) Math.floor(5.5341)); // 5
        System.out.println((int) Math.ceil(5.5341)); // 6
    }
}
```
주의 : 

반환타입이 다르다.

- round 반환 타입 :

float → int

double → long

이런 형식으로 반환하여 **정수**로 반환된다.

- floor, ceil의 반환타입 :

항상 **double**이므로 소숫점 반환을 주의해야 한다.


<br><br>
### 4. Math.pow(), Math.sqrt()

제곱 : Math.pow()

제곱근 : Math.sqrt()

예시 :
```java
public class Sample {
    public static void main(String[] args) {
        System.out.println((int) Math.pow(5, 2)); // 25
        System.out.println((int) Math.sqrt(25)); // 5
    }
}
```
Math.pow(a,b)는 a에 대하여 b만큼 제곱하겠다는 의미다.

Math.sqrt(a)는 a의 제곱근을 구하겠다는 의미이다.

주의 :

반환타입이 double이기에 소숫점 반환을 주의해야 한다.
