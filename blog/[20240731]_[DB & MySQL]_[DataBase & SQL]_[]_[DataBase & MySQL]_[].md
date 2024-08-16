# 1. 데이터베이스와 SQL

## 1) 데이터베이스란?

    데이터베이스란 여러 사람들이 '공유'할 목적으로 '통합하여 관리'하는 데이터의 집합 (쉽게 말해 데이터를 쌓는 창고)

## 2) DBMS란?

    'DataBase Management System'의 약자로 데이터베이스를 관리하는 시스템이라는 의미
     - 데이터베이스: 데이터를 넣는 창고
     - DBMS: 물건을 운송하는 트럭

## 3) SQL이란?

    SQL은 Structured Query Language의 약자로 이름에서 알 수 있듯이 언어의 한 종류이다.

    데이터베이스에서 데이터를 추가, 조회, 수정, 삭제하는데 사용한다.

    추가(Create), 조회(Read), 수정(Update), 삭제(Delete)의 앞 글자를 따 'CRUD'라고 부르기도 한다.

    데이터를 정의, 조작 제어하는 목적에 따라 크게 세가지로 구분한다.
     1. DDL(Data Definition Language)
     2. DML(Data Manipulation Language)
     3. DCL(Data Control Language)
    
| 속성 | 설명 | 주요 명령어 |
| --- | --- | --- |
| DDL | 데이터베이스나 테이블 등을 생성, 삭제하거나 그 구조를 변경하기 위한 명령어 | CREATE, ALTER, DROP |
| DML | 데이터베이스에 저장된 데이터를 처리하거나 조회, 검색하기 위한 명령어 | INSERT, UPDATE, DELETE, SELECT 등 |
| DCL | 데이터베이스에 저장된 데이터를 관리하기 위하여 데이터의 보안성 및 무결성 등을 제어하기 위한 명령어 | GRANT, REVOKE 등 |

## 4) RDBMS

    Relational Database Management System의 약자

    RDBMS는 관계형 데이터베이스라고 하며 데이터를 2차원의 테이블 구조로 저장한다.
[고객 정보를 저장하는 테이블]

| 고객 ID | 이름 | 주소 | 연락처 |
| --- | --- | --- | --- |
| 1 | 홍길동 | 서울 | 010-1234-5678 |
| 17 | 전우치 | 대구 | 010-9876-5432 |
    테이블은 행(가로)과 열(세로)로 구성된다.

    위의 예시에서 `고객 ID`는 고객 고유 식별자(키)이다.

## 5) 관계형 데이터베이스 특징

    어떤 쇼핑몰에서 사용하는 관계형 데이터베이스가 있을 때, 쇼핑몰에서 사용하는 수많은 데이터가 있다.
    지금은 아래 두 가지 테이블을 예시로 들자면

[고객 정보 테이블]
| 고객 ID | 이름 | 주소 | 연락처 |
| --- | --- | --- | --- |
| 1 | 동해물 | 서울 | 010-1234-5678 |
| 2 | 백두산 | 부산 | 010-8765-4321 |

[주문 정보 테이블]
| 주문번호 | 고객 ID | 주문일시 | 배송지 | 결제수단 | 총금액 | 배송비 |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 1 | 2023-11-12 | 서울 | 신용카드 | 10,000원 | 2,500원 |
| 2 | 1 | 2023-11-13 | 서울 | 신용카드 | 20,000원 | 2,500원 |
| 3 | 2 | 2023-11-12 | 부산 | 계좌이체 | 30,000원 | 3,000원 |

    위의 테이블을 보면 고객 정보와 주문 정보는 어떠한 관계가 있다는 것을 알 수 있다.

    고객 ID가 1번인 사람이 두 번의 주문을 했고, 고객 ID가 2번인 사람은 한 번의 주문을 했는데, 여기서 한 명의 고객은 여러 개의 주문을 할 수 있다. 이를 고객과 주문은 1:N 관계라고 한다.
    
    관계형 데이터베이스는 **테이블 간의 관계를 정의**하여 **데이터 사이의 연관성을 표현한다.**
     - 1:1 관계: 한 개의 행이 다른 한 개의 행에 대응
     - 1:N 관계: 한 개의 행이 다른 여러 개의 행에 대응
     - N:M 관계: 여러 개의 행이 다른 여러 개의 행에 대응

## 6) 데이터베이스 용어

1. 테이블(Table)
    - 데이터베이스에서 데이터를 구성하기 위한 가장 기본적인 단위
    - 행과 열로 구성되며 행은 여러 속성으로 구성
2. 행(Row)
    - 테이블의 구성 요소 중 하나이며, 테이블의 가로로 배열된 데이터의 집합
    - 행은 반드시 고유한 식별자인 기본키를 가진다.
    - 레코드(record) 라고 부르기도 한다.
3. 열(Column)
    - 테이블의 구성 요소 중 하나이며, 행에 저장되는 유형의 데이터
    - 데이터에 대한 무결성 보장(도메인)
        - e.g. 이름은 문자열, 나이는 숫자형
4. 기본키(Primary Key)
    - 행을 구분할 수 있는 **식별자**
    - 테이블에서 유일해야하며 중복 값을 가질 수 없다.
    - 데이터의 수정, 삭제, 조회에 사용
    - 다른 테이블과 관계를 맺어 데이터를 가져올 수도 있다.
        - e.g. `JOIN`
    - 기본키의 값은 수정되어서는 안되며 유효한 값이어야 한다.
        - `null`값이 될 수 없다.
5. 쿼리(Query)
    - 데이터를 조회하거나 삭제, 생성, 수정 같은 처리를 하기 위해 사용하는 명령문
    - **SQL** 이라는 데이터베이스 전용 언어를 사용하여 작성

# 2. DML, DDL, DCL

## 1) DML(Data Manipulation Language)이란

- 데이터베이스에서 데이터를 조작하는데 사용
- DML이라는 언어가 따로 있는건 아니고 SQL의 **하위 집합**이라고 이해하면 된다.
    - SQL을 이용하여 데이터를 조회, 삽입, 수정, 삭제하기 위한 문법
- 일반적으로 사용하는 DML문
    - SELECT: 조회
    - INSERT: 삽입
    - UPDATE: 수정
    - DELETE: 삭제

## 2) DDL(Data Definition Language)이란

- 해석하면 데이터를 정의하는 언어
- 데이터를 어떻게 저장할 지 전체적인 골격을 결정한다.
- 종류
    - CREATE: 새로운 테이블 생성
    - ALTER: 기존 테이블 구조 변경
    - DROP: 테이블 삭제
    - RENAME: 테이블 이름 변경
    - TRUNCATE: 테이블 초기화

## 3) DCL(Data Control Language)이란

- 사용 목적
    1. 데이터베이스를 다룰 수 있는 **권한**을 부여하거나 박탈
    2. 트랜잭션(Transaction) 관리
        - 트랜잭션이란 하나의 기능을 수행하기위한 **하나의 논리적인 작업 단위**
- 종류
    - GRANT: 권한 부여
    - REVOKE: 권한 박탈
    - COMMIT: 트랜잭션 적용
    - ROLLBACK: 트랜잭션 취소, 복구

# 3. SQL 쿼리문 코드

### DML, DDL, DCL 순서대로 작성

```sql
## ---------- DML ---------- ##
# ---------- Create(생성) ---------- #
# 작업할 데이터베이스 설정
USE my_db;

# 데이터 삽입: id가 11인 서울에 사는 30세 아나운서 박찬호
INSERT INTO person (id, name, age, address, job)
VALUES (11, '박찬호', 30, '서울특별시', '아나운서'); # 숫자는 ''를 사용하지 않음

# 여려 행 동시 삽입
INSERT INTO person (id, name, age, address, job)
VALUES (12, '박지훈', 27, '서울특별시', '가수'), # ,뒤에서 개행
(13, '이천수', 36, '서울특별시', '축구선수');

# 조회 후 삽입: name이 '이천수'인 데이터를 조회 후 id 14로 복사
INSERT INTO person (id, name, age, address, job)
SELECT 14, name, age, address, job
FROM person WHERE name = '이천수';

# ---------- Read(조회) ---------- #
USE my_db;

# person 테이블 내 모든 열 조회
SELECT * FROM person;
-- select * from person; # 가독성과 표준 관행을 위해 키워드는 대문자 사용

# 이름과 직업만 조회
SELECT name, job FROM person;

# 별칭 사용: 이름에 해당하는 열을 column1로 나이는 column2로 변경 후 출력
SELECT name AS column1, age AS column2 FROM person;

# 조건 사용: 나이가 29보다 많은 사람의 이름만 출력
SELECT name FROM person WHERE age > 29;

# 중복 제거: 주소를 출력하되 중복되지 않게 출력
SELECT DISTINCT address FROM person;

# ---------- Update(수정) ---------- #
USE my_db;

# 하나의 필드 수정: 'id'가 12인 레코드의 'age' 필드를 22로 변경
UPDATE person
SET age = 22
WHERE id = 12;

# 여러 필드 수정: 'id'가 10인 레코드의 'age'를 25로, 'job'을 '대학생'으로 변경
UPDATE person
SET age = 25, job = '대학생'
WHERE id = 10;

# 조건부 필드 수정: 'id'가 13 이상인 모든 레코드의 'address'를 '대전'으로 변경
UPDATE person
SET address = '대전'
WHERE id >= 13;

# ---------- Delete(삭제) ---------- #
USE my_db;

# id가 14인 데이터 삭제
DELETE FROM person
WHERE id=14;

# id가 11부터 13까지인 데이터 삭제
DELETE FROM person
WHERE id BETWEEN 11 AND 13;

# 모든 데이터 삭제 (주의!)
DELETE FROM person;

# ---------- 내장함수 ---------- #
USE my_db;

# 모든 사람의 나이 합계
SELECT SUM(age) FROM person;

# 모든 사람의 평균 나이
SELECT AVG(age) FROM person;

# 나이는 음수가 될 수 없으므로 절댓값으로 변환 후 삽입
INSERT INTO person (id, name, age, address, job)
VALUES (11, '김수현', ABS(-30), '서울', '기자');

# 입력된 값보다 작거나 같은 최대 정수를 반환: 양수의 경우 소수점 이하의 값 절사 (버림)
SELECT FLOOR(AVG(age)) FROM person;

# 가장 나이가 많은 사람의 나이
SELECT MAX(age) FROM person;

# 가장 나이가 적은 사람의 나이
SELECT MIN(age) FROM person;

# 'age' 열에 있는 값의 개수를 반환 (중복 포함)
SELECT COUNT(age) FROM person;

# 'age' 열에 있는 고유한 값의 개수를 반환 (중복 제외)
SELECT COUNT(DISTINCT age) FROM person;

# 두 문자열 연결: "고진용은 성남에 살고 있습니다."
SELECT CONCAT(name, '은 ', address, '에 살고 있습니다.')
FROM person WHERE id = 7;

# 'address' 열의 값과 해당 값의 길이 출력
SELECT address, CHAR_LENGTH(address) FROM person;

# 'address' 열의 값에서 '성'을 '경'으로 변경
SELECT REPLACE(address, '성', '경') FROM person;

# 현재 날짜와 시간 출력
SELECT NOW();

# ---------- 그룹화, 정렬 ---------- #
USE my_db;

# 데이터를 '주소' 기준으로 그룹핑 후 그룹별 인원수 구하기
SELECT address, COUNT(*)
FROM person
GROUP BY address;

# 데이터를 '주소' 기준으로 그룹핑 후 인원수가 2이상인 그룹 필터링
SELECT address, COUNT(*)
FROM person
GROUP BY address
HAVING COUNT(*) >= 2;

# 나이가 많은 순(내림차순 정렬)으로 조회
SELECT * FROM person
ORDER BY age DESC;

# 나이가 적은 순(기본값: 오름차순 정렬)으로 조회
SELECT * FROM person
ORDER BY age;

# 주소별로 거주하는 사람 수 집계
SELECT address, COUNT(*)
FROM person
WHERE age >= 35 # 필터링: 35세 이상
GROUP BY address
HAVING COUNT(*) = 1 # 필터링: 한 명만 거주하는 주소
ORDER BY address DESC; # 주소를 내림차순으로 정렬

# ---------- 조인 ---------- #
USE my_db;

# food 테이블 생성
CREATE TABLE food (
    name VARCHAR(50) NOT NULL,
    food_name VARCHAR(50) NOT NULL
);

# 음식 데이터 삽입
INSERT INTO food (name, food_name) VALUES
('김기태', '육회'),
('이창용', '비빔밥'),
('지공섭', '양주'),
('나재견', '라면'),
('최재훈', '불고기'),
('허독수', '치킨'),
('고진용', '짜장면'),
('곽지창', '호두'),
('마태수', '갈비'),
('왕석두', '파인애플'),
('김수현', '김치찜'),
('김기태', '초밥'),
('이창용', '돈까스'),
('최재훈', '떡볶이');

# 일반적으로 INNER JOIN 사용: 만약 person에만 있고 food에는 없다면 결과로 보이지 않음 (교집합 데이터 출력)
# FULL OUTER JOIN 사용 시 NULL값으로 채워서 출력, 그러나 MySQL에서는 지원하지 않음

# 모든 사람 정보 (person)과 모든 음식 정보 (food)가져오기 AS구문으로 별칭을 사용하여 코드 가독성을 향상
SELECT *
FROM person AS P
	INNER JOIN food AS F
	ON P.name = F.name; # 조인 조건: 이름이 같은 사람과 음식만 연결 (완전 일치 조건)

# 별칭 제거
SELECT *
FROM person
	INNER JOIN food
	ON person.name = food.name;

# 30세 미만인 모든 사람 정보(person 테이블)를 가져오기: person 테이블과 food 테이블을 왼쪽 외부 조인(LEFT OUTER JOIN)으로 연결
SELECT *
FROM person
  LEFT OUTER JOIN food
    ON person.name = food.name # 조인 조건: 이름이 같은 사람과 음식만 연결 (완전 일치 조건)
WHERE person.age < 30; # 30세 미만인 사람만

-- 모든 음식 정보(food 테이블)를 가져오기: food 테이블과 person 테이블을 오른쪽 외부 조인(RIGHT OUTER JOIN)으로 연결
SELECT *
FROM food
  RIGHT OUTER JOIN person
    ON food.name = person.name # 조인 조건: 이름이 같은 사람과 음식만 연결 (완전 일치 조건)
WHERE person.age >= 30; # 30세 이상인 사람만 필터링

# ---------- UNION ---------- #
USE my_db;

# 30세 미만인 사람과 35세 초과인 사람의 이름과 나이를 가져오고 UNION 을 사용하여 중복된 레코드 제거
SELECT name, age FROM person WHERE age < 30
UNION
SELECT name, age FROM person WHERE age > 35;

# 30세 미만인 사람과 35세 초과인 사람의 이름과 나이를 가져오고, UNION ALL 을 사용하여 모든 레코드 가져오기
SELECT name, age FROM person WHERE age < 30
UNION ALL
SELECT name, age FROM person WHERE age > 35;

# ---------- 서브 쿼리 ---------- #
USE my_db;

# 이름, 나이, 나이의 평균 조회
SELECT name, age, (SELECT AVG(age) FROM person) AS avg_age
FROM person
WHERE age < 30;

# 'food' 테이블에서 음식 이름이 '육회' 또는 '라면'인 데이터 추출
SELECT *
FROM (
		SELECT name, food_name
		FROM food
		WHERE food_name IN ('육회', '라면')
	 ) as vt; # 서브 쿼리의 결과를 가상 테이블처럼 사용
     
# WHERE절에 해당하는 이름을 가진 사람의 정보 뽑아내기
SELECT name, age, address, job
FROM person
WHERE name IN ( # 'food' 테이블에서 음식 이름이 '김치찜' 또는 '갈비'인 레코드의 이름만 추출해서
	SELECT name
	FROM food
	WHERE food_name IN ('김치찜', '갈비', '양주', '호두')
);

## ---------- DDL ---------- ##
USE my_db;

# 'students'테이블 생성
CREATE TABLE students (
  name VARCHAR(255) NOT NULL,
  age INT NOT NULL,
  address VARCHAR(255) NOT NULL
);

# 'person'테이블에 'college'라는 이름의 열을 추가: 이 열은 VARCHAR(50) 데이터 타입 사용
ALTER TABLE person ADD college VARCHAR(50);

# 'college'열 이름을 'university'로 변경
ALTER TABLE person RENAME COLUMN college TO university;

# 'university'열 데이터 타입을 VARCHAR(25)로 변경: (※주의) 데이터 타입 변경 시 기존 열에 저장된 데이터가 새 데이터 타입에 맞는지 확인
ALTER TABLE person MODIFY COLUMN university VARCHAR(25);

# 'person'테이블에서 'university'열 삭제
ALTER TABLE person DROP COLUMN university;

# 'students'테이블 삭제
DROP TABLE students;

# 'food'테이블의 모든 데이터 삭제
TRUNCATE TABLE food;

# 'person'테이블에 'name'열을 기준으로 하는 'person_index'인덱스 생성
CREATE INDEX person_index ON person (name);

# 'person'테이블에서 'person_index'인덱스 삭제
ALTER TABLE person DROP INDEX person_index;

## ---------- DCL ---------- ##
USE my_db;

# 특정 사용자의 특정 테이블에 대한 권한 박탈
REVOKE [권한] ON [테이블명] FROM [권한을 박탈할 사용자];

# 특정 사용자에게 특정 테이블에 대한 권한 부여
GRANT [권한] ON [테이블명] TO [권한을 받을 사용자];

# 사용자 'steve'의 'person' 테이블에 대한 SELECT 권한 박탈
REVOKE SELECT ON person FROM 'steve';

# 사용자 'james'에게 'person' 테이블에 대한 INSERT 권한 부여
GRANT INSERT ON person TO 'james';

# COMMIT 문법
COMMIT;

# ROLLBACK 문법
ROLLBACK;

# ----- COMMIT 예시 ----- #
# 트랜잭션 시작
START TRANSACTION;

# person 테이블에 새로운 데이터 삽입
INSERT INTO person (id, name, age) VALUES (1, 'Alice', 30);

# 변경 사항 저장
COMMIT;

# ----- ROLLBACK 예시 (에러가 발생했을 때 수행) ----- #
# 트랜잭션 시작
START TRANSACTION;

# person 테이블에 새로운 데이터 삽입
INSERT INTO person (id, name, age) VALUES (2, 'Bob', 25);

# 오류를 강제로 발생시키기 위한 잘못된 SQL 문 작성 (예시를 위해 잘못된 테이블명 사용)
INSERT INTO wrong_table (id, name, age) VALUES (3, 'Charlie', 40);

# 오류가 발생하여 ROLLBACK 수행
ROLLBACK;

## ----------DB 정렬 설정 확인 ---------- ##
# 정렬 설정 확인 쿼리문

# 데이터베이스의 정렬 설정 확인
SELECT SCHEMA_NAME, DEFAULT_COLLATION_NAME 
FROM information_schema.SCHEMATA 
WHERE SCHEMA_NAME = 'movieblog'; # ''안 DB명

# 테이블의 정렬 설정 확인
SHOW TABLE STATUS 
WHERE Name = 'post'; # ''안 테이블명 입력

# 컬럼의 정렬 설정 확인
SHOW FULL COLUMNS FROM post; # 테이블명 입력
```