## 컴파일 해보기

IntelliJ에서 터미널로 컴파일 해보자

### 1. 버전 확인

```bash
java -version

javac -version
```

![버전확인](img/java_terminal_compile/1.png)

정상적으로 설치되어 있다.

### 2. 테스트 파일

```java
public class Test {
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```

![테스트 파일 생성](img/java_terminal_compile/2.png)

src 폴더 내 Test.java로 컴파일 해본다.

### 3. 파일이 있는 디렉토리 찾아가기

```bash
cd src
```

![파일 찾아가기](img/java_terminal_compile/3.png)

### 4. 컴파일 전 파일 확인

```bash
dir
```

![파일 확인](img/java_terminal_compile/4.png)

### 5. 컴파일

아래 코드 입력 후 아무것도 나타나지 않으면 정상 실행된 것이다.

```bash
javac Hello.java
```

![컴파일](img/java_terminal_compile/5.png)

### 6. 컴파일 후 파일 확인

```bash
dir
```

![컴파일 후 파일 확인](img/java_terminal_compile/6.png)

컴파일러가 "Test.class"라는 파일을 생성(보통은 소스 파일과 같은 디렉터리에 생성)한 것을 볼 수 있다.

### 7. 파일 실행

```bash
java Test
```

![파일 실행](img/java_terminal_compile/7.png)

### 8. 마지막 폴더 내 파일 확인

![파일 확인](img/java_terminal_compile/8.png)

Test.class 파일이 추가되어 있다.