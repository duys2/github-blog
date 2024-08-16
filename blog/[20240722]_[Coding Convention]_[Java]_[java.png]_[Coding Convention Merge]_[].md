# Git Branch Convention

### 1. Branch Structure

---

- Branch 구조 (Serve Branch에서만)
    
    > Branch Type/Issue 번호 - Issue 명(기능 명)
    > 

### 2. Branch Type

---

- Main Branch
    - **main(master) :** 배포 가능한 상태의 결과물, release 타겟
    - **develop :** 구현한 기능을 병합하기 위한 branch, 통합 폴더의 기능
- Serve Branch
    - **feature :** 새로운 기능을 개발할 때 기능별 branch를 만들어 작업
    - **release** : 배포 하기 전 내용을 QA(품질 검사)하기 위한 브랜치, main과 devlop에 병합
    - **hotfix :** release 이후 버그가 발생 시 main(master)에서 분기 후 수정, main과 devlop에 병합
        
        ```
        feature/12-로그인
        hotfix/3-회원가입-버그
        ```
        

### 3. Merge 관련

---

- PR은 GitHub를 통해 수락
- PR 전 develop에서 먼저 merge 받아와 최신화 할 것 (충돌 해결)
    
    [PR 전 develop에서 먼저 Merge 받아와 최신화](https://www.notion.so/PR-develop-Merge-fecc73582bc14f45bc5bf7df2c33d465?pvs=21)
    

# Git Commit Convention

### 1. Commit Message Structure

---

- 기본적인 커밋 메시지 구조
    
    > 제목 ([Type] Subject) | 본문 (Body) | 꼬리말 (Footer)
    > 
    - 각 파트는 **빈 줄**을 두어 구분한다.
    - 제목은 필수이고, 나머지는 선택사항
- 작성 방법
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/7e384933-64e5-41a7-bc8a-5c234f1eb268/Untitled.png)
    
    ```bash
    git commit -m "[Type] Subject" -m "Body" -m "Footer"
    ```
    
    ```bash
    git commit -m "[Type] Subject
    
    Body
    
    Footer
    "
    ```
    

### 2. Commit Type (Subject)

---

- 커밋의 타입 구성
    
    > ‘[태그] 제목’으로 [] 뒤에만 공백을 넣는다.
    > 
    
    | Tag Name | Description |
    | --- | --- |
    | Feat | 새로운 기능을 추가 |
    | Add | 기존 내용 중 기능을 더 추가 |
    | Fix | 버그 수정 |
    | Design | CSS 등 사용자 UI 디자인 변경 |
    | !BREAKING CHANGE | 커다란 API 변경의 경우 |
    | !HOTFIX | 급하게 치명적인 버그를 고쳐야 하는 경우 |
    | Style | 코드 스타일 혹은 포맷 변경, 세미콜론 누락, 코드 수정이 없는 경우 |
    | Refactor | 프로덕션 코드 리팩토링 |
    | Comment | 필요한 주석 추가 및 변경 |
    | Docs | 문서 수정 |
    | Test | 테스트 코드, 리펙토링 테스트 코드 추가, Production Code(실제로 사용하는 코드) 변경 없음 |
    | Chore | 빌드 업무 수정, 패키지 매니저 수정, 패키지 관리자 구성 등 업데이트, Production Code 변경 없음, 그 외 자잘한 수정 |
    | Rename | 파일 혹은 폴더 명을 수정하거나 옮기는 작업만인 경우 |
    | Remove | 파일을 삭제하는 작업만 수행한 경우 |
    | Backup | 백업하는 경우 |
    | Init | 프로젝트 초기화 |
    | WIP | 진행 중인 작업 |
    | Build | 빌드 파일 수정 |
    | Perf | 성능 개선(최적화) |
    
    ```
    [Feat] navigation
    [Fix] db
    ```
    

### 3. Subject

---

- 제목은 50글자 이내로 작성한다.
- 마침표 및 특수 기호는 사용하지 않는다.
- 영문의 경우 첫 글자는 대문자로 작성한다.
- 영문으로 작성하는 경우 동사(원형)을 가장 앞에 명령어로 작성한다.
- 과거 시제는 사용하지 않는다.
- 개조식 구문(간결하고 요점적)으로 작성한다.
    
    ```
    Fixed → Fix
    ```
    

### 4. Body

---

- 72글자 이내로 작성한다.
- 최대한 상세히 작성한다. (코드 변경의 이유를 명확히 작성할수록 좋다)
- 어떻게 변경했는지 보다 무엇을, 왜 변경했는지 작성한다.

### 5. Footer

---

- Footer
    - Issue Tracker ID 작성에 사용
    - `유형: #이슈 번호` 형식으로 작성
    - 여러 개의 이슈 번호를 적을 때는 `쉼표(,)`로 구분한다.
    - 이슈 트래커 유형은 다음 중 하나를 사용한다.
        - 해결 관련
            - `Fixes`: 이슈 수정 중 (아직 해결되지 않은 경우)
            - `Resolves`: 이슈를 해결했을 때 사용
            - `Closes`: 종료
        - 참고 관련
            - `Ref`: 참고할 이슈가 있을 때 사용
            - `Related to`: 해당 커밋에 관련된 이슈번호 (아직 해결되지 않은 경우)
            - `See also`: 참고
    - 예시
        - `Fixes: #45`
        - `Closes #13, #24`

### 6. Example

---

- 예시
    - **예시 1**
        
        ```
        [Feat] 회원 가입 기능 구현
        
        SMS, 이메일 중복확인 API 개발
        
        Resolves: #123
        Ref: #456
        ```
        
    - **예시 2**
        
        ```
        [Feat] Summarize changes in around 50 characters or less
        
        More detailed explanatory text, if necessary. Wrap it to about 72
        characters or so. In some contexts, the first line is treated as the
        subject of the commit and the rest of the text as the body. The
        blank line separating the summary from the body is critical (unless
        you omit the body entirely); various tools like `log`, `shortlog`
        and `rebase` can get confused if you run the two together.
        
        Explain the problem that this commit is solving. Focus on why you
        are making this change as opposed to how (the code explains that).
        Are there side effects or other unintuitive consequences of this
        change? Here's the place to explain them.
        
        Further paragraphs come after blank lines.
        
        - Bullet points are okay, too
        
        - Typically a hyphen or asterisk is used for the bullet, preceded
        by a single space, with blank lines in between, but conventions
        vary here
        
        If you use an issue tracker, put references to them at the bottom,
        like this:
        ```
        
    - **예시 3**
        
        ```
        [Feat] Summarize changes in around 50 characters or less
        
        More detailed explanatory text, if necessary. Wrap it to about 72
        characters or so. In some contexts, the first line is treated as the
        subject of the commit and the rest of the text as the body. The
        blank line separating the summary from the body is critical (unless
        you omit the body entirely); various tools like `log`, `shortlog`
        and `rebase` can get confused if you run the two together.
        
        Explain the problem that this commit is solving. Focus on why you
        are making this change as opposed to how (the code explains that).
        Are there side effects or other unintuitive consequences of this
        change? Here's the place to explain them.
        
        Further paragraphs come after blank lines.
        
         - Bullet points are okay, too
        
         - Typically a hyphen or asterisk is used for the bullet, preceded
           by a single space, with blank lines in between, but conventions
           vary here
        
        If you use an issue tracker, put references to them at the bottom,
        like this:
        
        Resolves: #123
        See also: #456, #789
        ```
        
    - **그 외 자주 쓰이는**
        
        ```
        [Fix] 버그 수정
        
        Fix my test
        Fix typo in style.css
        Fix my test to return undefined
        Fix error when using my function
        
        Update : Fix와 달리 원래 정상적으로 동작했지만 보완의 개념
        Update harry-server.js to use HTTPS
        
        Add
        Add documentation for the defaultPort option
        Add example for setting Vary: Accept-Encoding header in zlib.md
        
        Remove(Clean이나 Eliminate) : ‘unnecessary’, ‘useless’, ‘unneeded’, ‘unused’, ‘duplicated’가 붙는 경우가 많음
        Remove fallback cache
        Remove unnecessary italics from child_process.md
        
        Refactor : 리팩토링
        
        Simplify : Refactor와 유사하지만 약한 수정, 코드 단순화
        
        Improve : 호환성, 테스트 커버리지, 성능, 검증 기능, 접근성 등의 향상
        Improve iOS's accessibilityLabel performance by up to 20%
        
        Implement : 코드 추가보다 큰 단위의 구현
        Implement bundle sync status
        
        Correct : 주로 문법의 오류나 타입의 변경, 이름 변경 등에 사용
        Correct grammatical error in BUILDING.md
        
        Prevent
        Prevent hello handler from saying Hi in hi.js
        
        Avoid : Prevent는 못하게 막지만, Avoid는 회피(if 등)
        Avoid flusing uninitialized traces
        
        Move : 코드나 파일의 이동
        Move function from header to source file
        
        Rename : 이름 변경
        Rename node-report to report
        ```
        

### 7. Commit Message Emoji ([gitmoji](https://gitmoji.dev/))

---

- 깃모지
    
    
    | Emoji | Description |
    | --- | --- |
    | 🎨 | 코드의 형식 / 구조를 개선 할 때 |
    | 📰 | 새 파일을 만들 때 |
    | 📝 | 사소한 코드 또는 언어를 변경할 때 |
    | 🐎 | 성능을 향상시킬 때 |
    | 📚 | 문서를 쓸 때 |
    | 🐛 | 버그 reporting할 때, @FIXME 주석 태그 삽입 |
    | 🚑 | 버그를 고칠 때 |
    | 🐧 | 리눅스에서 무언가를 고칠 때 |
    | 🍎 | Mac OS에서 무언가를 고칠 때 |
    | 🏁 | Windows에서 무언가를 고칠 때 |
    | 🔥 | 코드 또는 파일 제거할 때 , @CHANGED주석 태그와 함께 |
    | 🚜 | 파일 구조를 변경할 때 . 🎨과 함께 사용 |
    | 🔨 | 코드를 리팩토링 할 때 |
    | ☔️ | 테스트를 추가 할 때 |
    | 🔬 | 코드 범위를 추가 할 때 |
    | 💚 | CI 빌드를 고칠 때 |
    | 🔒 | 보안을 다룰 때 |
    | ⬆️ | 종속성을 업그레이드 할 때 |
    | ⬇️ | 종속성을 다운 그레이드 할 때 |
    | ⏩ | 이전 버전 / 지점에서 기능을 전달할 때 |
    | ⏪ | 최신 버전 / 지점에서 기능을 백 포트 할 때 |
    | 👕 | linter / strict / deprecation 경고를 제거 할 때 |
    | 💄 | UI / style 개선시 |
    | ♿️ | 접근성을 향상시킬 때 |
    | 🚧 | WIP (진행중인 작업)에 커밋, @REVIEW주석 태그와 함께 사용 |
    | 💎 | New Release |
    | 🔖 | 버전 태그 |
    | 🎉 | Initial Commit |
    | 🔈 | 로깅을 추가 할 때 |
    | 🔇 | 로깅을 줄일 때 |
    | ✨ | 새로운 기능을 소개 할 때 |
    | ⚡️ | 도입 할 때 이전 버전과 호환되지 않는 특징, @CHANGED주석 태그 사용 |
    | 💡 | 새로운 아이디어, @IDEA주석 태그 |
    | 🚀 | 배포 / 개발 작업 과 관련된 모든 것 |
    | 🐘 | PostgreSQL 데이터베이스 별 (마이그레이션, 스크립트, 확장 등) |
    | 🐬 | MySQL 데이터베이스 특정 (마이그레이션, 스크립트, 확장 등) |
    | 🍃 | MongoDB 데이터베이스 특정 (마이그레이션, 스크립트, 확장 등) |
    | 🏦 | 일반 데이터베이스 별 (마이그레이션, 스크립트, 확장명 등) |
    | 🐳 | 도커 구성 |
    | 🤝 | 파일을 병합 할 때 |

# Code Convention

### 1. Naming Rule

---

- 공통
    
    > 대소문자를 구분하며, 길이에 제한이 없다.
    > 
    > 
    > → e.g. 변수명은 의미 부여를 명확하게, 주석 사용 지양
    > 
    > 예약어는 사용하지 않는다.
    > → java 예약어 (e.g. `class, import, while, break` 등)
    > 
    > 숫자로 시작하면 안된다.
    > 
    > 특수문자는 '_(언더바)'와 '$' 만 허용한다.
    > 
    > 표기법
    > 
    > - Pascal Case: 첫 글자와 중간 글자들이 모두 대문자
    > - Camel Case: 중간 글자들은 대문자로 시작하지만 첫 글자가 소문자로 시작
    > - **Snake Case:** 언더바(_) 가 들어 있는 표현 방식
    > 
    > 반의어는 반드시 대응하는 개념으로 사용해야 한다.
    > 
- 명명 규칙
    
    > 클래스명은 PascalCase로 작성 (예시: `UserManager`)
    →  Enum, Interface, Annotation type 등 포함
    변수와 메서드명은 camelCase 사용 (예시: `isActive`, `processUser`)
    → 동사로 시작
    상수는 영문 대문자 스네이크 표기법 사용 (예시: `MAX_RETRY_COUNT`)
    > 
- 파일명
    
    > 파일명은 포함된 소스의 최상위 클래스의 이름과 `.java` 확장자로 구성
    > 
- 제네릭 타입 매개변수 명
    
    > 둘 중 하나로 작성
    > 
    > 
    > 1. 대문자 한 글자, 거기에 숫자 하나는 옵션으로 가능 (e.g. `E, T, T2`)
    > 
    > 2. 클래스 이름 + T를 붙인다. (e.g. `RequestT`)
    > 
- 패키지명
    
    > 모두 소문자로만 작성
    → `com.company.spring`
    > 

### 2. Code Style

---

- Java
    
    > ▶ **접근 제어자**
    → 적절한 접근 제어자 사용 (private, public 등)
    → 변수는 일반적으로 `private`으로 선언 (상수는 예외)
    
    ▶ **변수 선언**
    > 
    > 
    > → 클래스 상단에 모아서 작성
    > 
    > → 상수는 `static final`로 선언
    > 
    > ▶ **import문**
    > 
    > **→ 클래스 선언문 위**에 작성
    > 
    > → 알파벳 순으로 정렬
    > 
    > → 와일드 카드(`*`) 사용 지양
    > 
    > ▶ **문장**
    > → 한 줄에 하나의 문장만 작성 (`;`로 구분)
    > 
    > → 긴 줄은 100자를 넘지 않도록 줄 바꿈
    > 
    > 불필요한 주석 대신 자체 설명적인 코드 작성 권장
    > 
    > → 최대한 의미있는 네이밍
    > 
    > ▶ **메서드**
    > 
    > → 메서드 사이에는 빈 줄을 넣어 가독성 향상
    > 
    > → 한 가지 기능만 수행하도록 작성 (단일 책임 원칙)
    > 
    > ▶ **코드 구조**
    > 
    > → 멤버 변수, 생성자, 메서드 등을 그룹화하여 정리
    > 
    > → 각 섹션에 주석으로 구분선 추가 (아래 주석 부분 참고)
    > 
    > ▶ **주석** (아래 주석 부분 참고)
    > 
    > → `//` 또는 `/* */`를 사용하여 코드 설명 추가
    > 
    > → 클래스와 중요 메서드에 JavaDoc 스타일 주석 사용
    > 
    > → 메서드 내부의 주요 로직에 인라인 주석 추가
    > 
    > → TODO, FIXME 등의 특별 주석 사용
    > 
    > - TODO: 코드에 추가해야 할 작업이나 향후 개선해야 할 부분 표시
    > - FIXME: 코드에서 발견된 문제점이나 버그 표시
    > 
    > ```java
    > // TODO: [해야 할 작업 내용]
    > // FIXME: [문제점 내용]
    > ```
    > 
    > ▶  **중괄호와 들여쓰기**
    > 
    > → 중괄호는 같은 줄에서 시작
    > 
    > → 일관된 들여쓰기 사용: 4칸
    > 
    > ▶ **조건문과 반복문**
    > 
    > → 단일 라인 조건문의 경우 중괄호 생략 가능
    > 
    > → `{` 뒤에서 줄바꿈
    > 
    > → 복잡한 조건문과 반복문은 중괄호 사용
    > 
    > ▶ **줄바꿈 규칙**
    > 
    > → 람다 표현식과 스트림 API 사용 시 가독성을 고려한 줄 바꿈
    > 
    > → 줄바꿈의 더 높은 구문 수준(**higher syntactic level**)에서 끊어주는 것을 원칙으로 한다.
    > 
    > → **연산자** 같은 상징들 (operator-like symbol)들 앞에서 끊어준다. 
    > 
    > → operator-like symbol 종류
    > 
    > - `.`
    > - 람다의 `::`
    > - <T extends Foo & Bar>와 같은 타입에서의 `&`
    > - catch(FooException | BarException e) 같은 캐치블록에서의 `|`
    > 
    > ```java
    > // 좋은 예
    > stream.filter(s -> s.length() > 10)
    >       .map(String::toUpperCase)
    >       .collect(Collectors.toList());
    > 
    > // 나쁜 예
    > stream.filter(s -> s.leng
    >       th() > 10).map(String::toUpper
    >       Case).collect(Collectors.toList());
    > ```
    > 
    > → `,`는 앞에 오는 토큰의 뒤에 적는다.
    > 
    > - **토큰**이란 프로그래밍 언어에서 의미 있는 최소 단위
    > 
    > ```java
    > // 좋은 예
    > int[] numbers = {1, 2, 3, 4, 5};
    > 
    > // 나쁜 예
    > int[] numbers = {1 , 2 , 3 , 4 , 5};
    > ```
    > 
    > **→** 줄바꿈 시 들여쓰기: 최초 행보다 **최소 4자** 들여쓰기 한다.
    > 
- 주석
    
    > **그룹(섹션)**으로 묶이면 `/* --------------- 내용 --------------- */`
    **함수 내부**에서 설명이 그룹으로 묶이면 `/* 내용 */`
    **기능 요약**은 코드 상단에 `// 내용`
    **메모, 주요로직 설명**은 코드 오른쪽에 `// 내용`
    **미사용 코드**는 아래쪽에 `// 내용`
    > 
    > 
    > ```java
    > public class UserManager {
    > 
    >     /* ---------- 멤버 변수 ---------- */
    >     private String userName; // 변수는 camelCase
    >     private int maxCount;
    > 
    >     /* ---------- 상수 ---------- */
    >     private static final int MAX_RETRY_COUNT = 3;
    >     private static final long TIMEOUT_SECONDS = 30;
    > 
    >     /* ---------- 생성자 ---------- */
    >     public UserManager(String userName) {
    >         this.userName = userName;
    >         this.maxCount = 100;
    >     }
    >     
    >     /* ---------- 접근자와 생성자 ---------- */
    >     public void setUserName(String name) {  // setter
    >         this.userName = name;
    >     }
    > 
    >     public String getUserName() {  // getter
    >         return this.userName;
    >     }
    > 
    >     /* ---------- 메서드 ---------- */
    >     public boolean isValidUser() {  // 메서드는 camelCase
    >         return validateUser(this.userName);
    >     }
    > 
    >     public void processUser() {
    > 		    /* 사용자의 활성 상태를 확인하여 적절한 메서드 호출 */
    >         if (isActive) {  // 중괄호는 같은 줄에 시작
    >             doActiveUserProcess();
    >         } else {
    >             handleInactiveUser();
    >         }
    > 
    >         // 단일 라인 조건문
    >         if (maxCount == 0) return;  // 인라인 주석: 같은 줄에 작성
    >     }
    > }
    > ```
    > 

### 3. 참고 링크

---

[Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)