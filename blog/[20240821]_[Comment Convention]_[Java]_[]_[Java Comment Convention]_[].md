# 주석

    `//` 또는 `/* */`를 사용하여 코드 설명 추가

    클래스와 중요 메서드에 JavaDoc 스타일 주석 사용

    메서드 내부의 주요 로직에 인라인 주석 추가

    TODO, FIXME 등의 특별 주석 사용
    - TODO: 코드에 추가해야 할 작업이나 향후 개선해야 할 부분 표시
    - FIXME: 코드에서 발견된 문제점이나 버그 표시

```java
// TODO: [해야 할 작업 내용]
// FIXME: [문제점 내용]
```

---

# 주석 스타일

    그룹(섹션)으로 묶이면 /* --------------- 내용 --------------- */
    함수 내부에서 설명이 그룹으로 묶이면 /* 내용 */
    기능 요약은 코드 상단에 // 내용
    메모, 주요로직 설명은 코드 오른쪽에 // 내용
    미사용 코드는 아래쪽에 // 내용

```java
public class UserManager {

    /* ---------- 멤버 변수 ---------- */
    private String userName; // 변수는 camelCase
    private int maxCount;

    /* ---------- 상수 ---------- */
    private static final int MAX_RETRY_COUNT = 3;
    private static final long TIMEOUT_SECONDS = 30;

    /* ---------- 생성자 ---------- */
    public UserManager(String userName) {
        this.userName = userName;
        this.maxCount = 100;
    }

    /* ---------- 접근자와 생성자 ---------- */
    public void setUserName(String name) { // setter
        this.userName = name;
    }

    public String getUserName() { // getter
        return this.userName;
    }

    /* ---------- 메서드 ---------- */
    public boolean isValidUser() { // 메서드는 camelCase
        return validateUser(this.userName);
    }

    public void processUser() {
        /* 사용자의 활성 상태를 확인하여 적절한 메서드 호출 */
        if (isActive) { // 중괄호는 같은 줄에 시작
            doActiveUserProcess();
        } else {
            handleInactiveUser();
        }

        // 단일 라인 조건문
        if (maxCount == 0) return; // 인라인 주석: 같은 줄에 작성
    }
}
```

---

# Java Doc

```java
/**
 * 메서드 요약 설명
 *
 * @author 작성자
 * @param 매개변수 설명
 * @return 반환값 설명
 */
```
| annotaion | Description | Example |
| --- | --- | --- |
| @author | 작성자 | @author 작성자 |
| @return | 반환값 |  |
| @param | 메소드의 매개변수 / 인자값 설명 |  |
| @exception | 발생할 수 있는 Exception 정의 |  |
| @throws | 코드에서 throw 할 수 있는 예외상황 정의 |  |
| @version | 구현체(클래스, 메소드,변수 등)의 버전 |  |
| @deprecated | 해당 구현체가 곧 삭제, 업데이트 중단을 의미 |  |
| @since | 해당 구현체가 추가된 버전 |  |
| @see | 외부 링크나 텍스트, 다른 필드나 메소드를 링크할 때 사용 | 외부 링크 : a href 태그 이용내부 참조 : 패키지명#생성자/ 필드 / 메소드명 |
| @link | see와 동일한 기능, 참조에 대한 링크 제공 |  |
| @serial | Serializable Interface에 사용 |  |
| @serialDate | writeObject writeExternal 메소드로 작성된 추가적 데이터를 설명 |  |
| @serialField | serialPersistnetFields 배열의 모든 필드에 사용 |  |