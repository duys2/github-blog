## 8) 컴파일 해보기

- cmd로 컴파일 해본다
    - javac: 컴파일러
    - java: 클래스 파일을 실행하는 가상 기계

1. 버전 확인

    ```bash
    java -version
    
    javac -version
    ```

   ![버전확인](img/java_compile/1.png)

   정상적으로 설치되어 있다.

2. 테스트 파일 생성

    ```java
    public class Hello {
        public static void main(String[] args) {
            System.out.println("Hello World");
        }
    }
    ```

   ![테스트 파일 생성](img/java_compile/2.png)

   C드라이브에 test 폴더를 생성 후 Hello.java를 생성했다.

3. 파일 찾아가기

    ```bash
    cd test
    ```

   ![파일 찾아가기](img/java_compile/3.png)

   디렉터리 찾아가기

4. 컴파일 전 파일 확인

    ```bash
    dir
    ```

   ![파일 확인](img/java_compile/4.png)

   디렉터리 찾아가기

5. 컴파일

   아래 코드 입력 후 아무것도 나타나지 않으면 정상 실행된 것이다.

    ```bash
    javac Hello.java
    ```

6. 컴파일 후 파일 확인

    ```bash
    dir
    ```

   ![컴파일 후 파일 확인](img/java_compile/6.png)

   컴파일러가 Hello.class라는 클래스 파일을 생성(보통은 소스 파일과 같은 디렉터리에 생성된다)한 것을 볼 수 있다.

7. 파일 실행

    ```bash
    java Hello.java
    
    java Hello
    ```

   ![파일 실행](img/java_compile/7.png)

   뒤에 .java를 붙여도 안 붙여도 실행은 잘 된다. 이에 대해선 추후에 추가로 학습해 보자.

8. 마지막 폴더 내 파일 확인

   ![파일 확인](img/java_compile/8.png)

   Hello.class 파일이 추가되어 있다.