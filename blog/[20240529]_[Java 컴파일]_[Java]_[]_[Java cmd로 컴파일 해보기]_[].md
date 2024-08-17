# 컴파일 해보기

- cmd로 컴파일 해본다
    - javac: 컴파일러
    - java: 클래스 파일을 실행하는 가상 기계

## 1. 버전 확인

```shell
java -version

javac -version
```

![버전확인](img/java_cmd_compile/1.png)

정상적으로 설치되어 있다.

## 2. 테스트 파일 생성

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

![테스트 파일 생성](img/java_cmd_compile/2.png)

C드라이브에 test 폴더를 생성 후 Hello.java를 생성했다.

## 3. 파일 찾아가기

```shell
cd test
```

![파일 찾아가기](img/java_cmd_compile/3.png)

디렉토리 찾아가기

## 4. 컴파일 전 파일 확인

```shell
dir
```

![파일 확인](img/java_cmd_compile/4.png)

디렉토리 찾아가기

## 5. 컴파일

아래 코드 입력 후 아무것도 나타나지 않으면 정상 실행된 것이다.

```shell
javac Hello.java
```

## 6. 컴파일 후 파일 확인

```shell
dir
```

![컴파일 후 파일 확인](img/java_cmd_compile/6.png)

컴파일러가 Hello.class라는 클래스 파일을 생성(보통은 소스 파일과 같은 디렉터리에 생성된다)한 것을 볼 수 있다.

## 7. 파일 실행

```shell
java Hello.java

java Hello
```

![파일 실행](img/java_cmd_compile/7.png)

## 8. 마지막 폴더 내 파일 확인

![파일 확인](img/java_cmd_compile/8.png)

Hello.class 파일이 추가되어 있다.

## 9. 다음 두 명령어의 차이는 무엇일까?
    7번 파일 실행 실습 당시 뒤에 .java를 붙여도 안 붙여도 실행은 잘 되었다.

    왜 이런 현상이 발생했을까? 이제부터 알아보자.

    1. java Hello.java 명령어는 자바 소스 코드 파일(.java)을 컴파일하고 직접 실행한다. 이 경우 Java 컴파일러가 파일을 메모리에 로드하고 즉시 실행한다
    
    2. java Hello 명령어는 이미 컴파일된 클래스 파일(바이트코드 파일: Hello.class)을 직접 실행한다.
### 결론
    java Hello.java는 소스 파일을 즉시 실행하고, java Hello는 미리 컴파일된 클래스 파일을 실행한다. 위의 실습에서는 위에서 javac Hello.java라는 명령어로 인해 Hello.class라는 클래스 파일이 생성되었기에 java Hello 명령어를 실행해도 차이가 없는 것처럼 보였던 것이다.