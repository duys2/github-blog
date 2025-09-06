# 1. Git과 GitHub

# 1) 버전 관리

- 버전 관리: 게임 등에서 내가 원하는 시점으로 이동할 수 있게 해 주는 것

## 2) Git

- 소스 코드를 추가할 때 오류가 발생하면 원하는 시점으로 복구할 수 있게 해주는 것이 소스 코드 버전 관리 시스템 Git이다.

## 3) GitHub

- Git으로 관리하는 프로젝트를 올려둘 수 있는 대표적인 Git 호스팅 사이트
    - 오픈소스: 누구나 기여할 수 있고, 접근 가능한 공개 저장소 프로젝트

# 2. Git 실습

## 1) 로컬 저장소 생성

### 1-1) `바탕 화면/git-learn/ronaldo`경로에 `README.txt` 생성

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/c43c83ba-5131-4819-8fee-5a36e6639b54/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/68ec964c-4bec-4f0a-a89e-031aad856dfb/Untitled.png)

### 1-2) 마우스 우클릭 후 메뉴에서 Git Bash Here 클릭

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/013627f8-1c89-4d24-936e-b9437ea46741/Untitled.png)

### 1-3) Git 초기화

- `git init` 명령어 실행

```bash
# 초기화
$ git init
```

- ‘Initialized empty Git repository’라는 텍스트가 나오면 성공

![~/OneDrive/바탕 화면/git-learn/ronaldo는 **현재** Git Bash가 **실행**되고 있는 내 컴퓨터의 경로](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/361c6f66-92c5-4cbe-adbf-0b06d715bb79/Untitled.png)

~/OneDrive/바탕 화면/git-learn/ronaldo는 **현재** Git Bash가 **실행**되고 있는 내 컴퓨터의 경로

- `.git` 폴더를 **로컬 저장소**라고 한다.
    - 하나의 폴더에는 하나의 .git(로컬 저장소)을 가져야 한다(충돌이 발생할 수 있다).

![만약 .git 폴더가 보이지 않는다면 폴더의 상단 메뉴의 보기 란에서 **숨김 속성 체크**](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/3725f639-5b22-4f2b-a5c9-0985b7c9c41f/Untitled.png)

만약 .git 폴더가 보이지 않는다면 폴더의 상단 메뉴의 보기 란에서 **숨김 속성 체크**

## 2) 커밋

- 커밋: Git에서 저장되어 생성된 하나의 버전

### 2-1) 유저 정보 입력

- 누가 커밋을 했는지를 확인하기 위해 정보를 등록해야 한다.

```bash
# 전역 사용자 이름 설정
git config --global user.name

# 전역 사용자 이메일 설정
git config --global user.email
```

- 나의 정보 입력하기

```bash
git config --global user.name "duys2"

git config --global user.email minigun5@naver.com
```

- 커밋할 때마다 위 정보가 사용되어 **누가** 어떤 변경을 했는지 추적하는 데 도움을 준다.
- 정보 확인

```bash
# 현재 설정된 사용자 이름 확인
git config --get user.name # duys2

# 현재 설정된 사용자 이메일 확인
git config --get user.email # minigun5@naver.com
```

### 2-2) 커밋하기

- 커밋할 파일 선택 후 스테이징 영역에 추가
    - 스테이징 영역이란: 간단하게 **커밋하려는 변경사항**들을 임시로 모아두는 공간

```bash
# 특정 파일을 스테이징 영역에 추가
git add 파일명

# 현재 디렉토리의 모든 변경사항을 스테이징 영역에 추가
git add .

# 여러 파일을 선택적(동시에)으로 스테이징 영역에 추가
git add 파일1 파일2 파일3

# README.txt 파일을 스테이징 영역에 추가
git add README.txt
```

- 커밋하기

```bash
# 스테이징된 변경사항을 커밋하고 커밋 메시지 작성
git commit -m "commit message" # -m은 'message'의 약자

git commit -m "[Feat] first commit"
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/03043814-4083-41f9-9793-2c7599ee4ea6/Untitled.png)

1 file changed, 1 insertion(+) 라는 메시지가 나오면 성공

- 파일 수정 후 커밋하기

![내용 수정](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/43a3f1a1-444f-4727-b1f9-ffb6821c8b93/Untitled.png)

내용 수정

```bash
git add README.txt

git commit -m "[Docs] 파일 내용 수정"
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/69f4ea0c-99ba-4bc1-9837-f89d5910537e/Untitled.png)

1 file changed, 1 insertion(+), 1 deletion(-) 가 뜨면 성공

### 2-3) 커밋 버전 변경

- 요구사항 변경 등으로 이전 커밋 버전으로 되돌리는 경우
- `git log` 명령어로 커밋 확인

```bash
git log
```

![노랗게 표시된 commit … 부분이 ‘커밋 아이디’이다.](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/4b7dd210-247e-410f-ab04-b78549e6468b/Untitled.png)

노랗게 표시된 commit … 부분이 ‘커밋 아이디’이다.

- 첫 번째 커밋으로 돌리기 위해 `git checkout` 명령어를 사용한다.
    - 이때 커밋 아이디는 앞 7자리만 사용하거나 전체를 사용해도 된다.

```bash
git checkout 커밋아이디

git checkout 133c575
```

- 파일 내용이 변경된 모습을 확인할 수 있다.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/493fcc57-4214-40b4-8fed-37748904a09c/Untitled.png)

HEAD is now at 133c575 [Feat] first commit 가 보이면 성공

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/e75927e9-39c1-4619-a963-c2edf91798d7/Untitled.png)

### 2-4) 최신 커밋으로 돌아가기

- `git checkout` 명령어 사용
    - 두 번째 커밋 아이디를 입력해도 되지만 이번에는 간략히 `-`만 입력

```bash
git checkout - # -는 "직전에 체크아웃했던 브랜치 또는 커밋"을 의미
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/9dfbe8db-0aa3-4ac2-8e4a-dd5d224c759d/Untitled.png)

![복구된 모습](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/51708d60-36e7-4930-807b-a6f8b592914b/Untitled.png)

복구된 모습

## 3) checkout

- `checkout` 명령어는 많은 기능을 포함하고 있어 주요 기능이 아래의 두 명령어로 나누어졌다.
    - `switch`: 브랜치 간 이동
    - `restore`: 커밋에서 파일 복구
- `checkout` 명령어를 통해 커밋 아이디를 지정해 되돌아가는 명령어는 다소 위험하기에 실무에서는 잘 사용하지 않는다고 한다.
    - 주의해서 사용하도록 하자.

# 3. GitHub 원격 저장소에 커밋 올리기

## 1) 원격 저장소 생성

- GitHub에서 원격 저장소를 **레포지토리(Repository)**라고 부른다.

![레포지토리 생성](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/5e5b03c7-b8d4-4bf0-82c3-6af175286026/Untitled.png)

레포지토리 생성

- 위 레포지토리의 주소는 아래와 같다.

```
https://github.com/duys2/git-learn.git
```

## 2) 원격 저장소에 커밋 올리기

- `git remote add origin` 명령어 사용

```bash
# 원격 저장소를 로컬 Git 저장소에 추가
git remote add origin <원격 저장소 주소> # 로컬 Git 저장소에 원격 저장소를 연결
```

```bash
# 삽입은 Shift Insert
git remote add origin https://github.com/duys2/git-learn.git
```

- 커밋 전에 브랜치를 바꾼다.
    - Git에선 Master란 브랜치를 default로 쓰고, Github에선 Master대신 Main으로 default를 쓰기 때문에 현재 브랜치 명을 Main으로 바꿔준다.
        - 물론 깃허브에서 기본 브랜치를 master로 설정해도 되지만 main이 편하기에 아래와 같이 진행한다.
    - `git branch` 명령어 사용

```bash
# 현재 브랜치(기본 브랜치)의 이름을 'main'으로 변경
git branch -M main
```

![잘 변경되었다.](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/ab41ab2a-ae95-4d28-a121-3c742e7c9067/Untitled.png)

잘 변경되었다.

- `git push` 명령어로 원격 저장소에 푸시하기(올리기)

```bash
# 로컬의 'main' 브랜치를 원격 저장소 'origin'의 'main' 브랜치로 푸시한다(올린다).
git push origin main
```

![이렇게 100% 완료 메시지가 나오면 성공](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/f9ddbc10-ee75-447d-8f12-50dd37efe117/Untitled.png)

이렇게 100% 완료 메시지가 나오면 성공

![잘 올라가 있는 모습](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/592283e5-9045-42df-be03-82b5dc26c4d5/Untitled.png)

잘 올라가 있는 모습

# 4. 원격 저장소의 커밋을 로컬 저장소에 내려받기

## 1) 클론

- 원격 저장소의 코드와 버전 전체를 내려받는 것을 **클론(Clone)**이라고 한다.
- `바탕 화면/git-learn/messi` 경로로 새 폴더 생성 후 Git Bash 열기
- `git clone` 명령어를 사용해 원격 저장소의 내용을 클론하기
    - 주소 입력 후 **한 칸 띄우고 마침표**를 찍는다.

```bash
# 원격 저장소의 내용을 현재 디렉토리에 복제
git clone <원격 저장소 주소> .
```

![원격 저장소 주소](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/9aa11877-1191-42c3-87a3-068e1287fb78/Untitled.png)

원격 저장소 주소

```bash
git clone https://github.com/duys2/git-learn.git .
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/730b5681-ad48-4852-80f8-fce7efc9de94/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/4417a5f0-1c2f-4328-bb2e-59a577aa1f1a/Untitled.png)

![클론 완료](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/e1768e51-4e54-4311-8e7e-7995dcc03d1d/Untitled.png)

클론 완료

## 2) 파일 수정 후 커밋하기

- 파일 확장자 변경 후 파일 내용 수정 (`.txt` → `.md`)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/492b558c-a0cf-4c15-87db-10c7094f77a9/Untitled.png)

- `git add .` 명령어 사용

```bash
# 현재 디렉토리의 모든 변경사항을 스테이징 영역에 추가
git add .
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/f8eaa5ca-8861-4f55-a09f-2192665fc028/Untitled.png)

- 커밋하기

```bash
git commit -m "[Docs] 파일 확장자 변경 및 내용 수정"
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/2468c385-e9e1-4ac2-9f9c-905d05508540/Untitled.png)

- 푸시하기

```bash
git push origin main
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/6a0aa709-5b16-4795-83cb-da8dae7739f4/Untitled.png)

![잘 올라가 있다.](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/59ae44e1-5817-46ef-a180-9ac083001a02/Untitled.png)

잘 올라가 있다.

## 3) 원격 저장소의 새로운 커밋을 로컬 저장소에 갱신하기

- messi는 최신 내용(커밋)이지만 ronaldo는 아니다.
- Git Bash를 열고 `git pull origin main` 명령어를 사용해 새로운 커밋을 받아온다.

```bash
# 원격 저장소 'origin'의 'main' 브랜치에서 변경사항을 가져와 현재 브랜치에 병합
git pull origin main
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/bca5aafc-47be-49d0-8e5f-d9aa2b6b85c0/Untitled.png)

![정상 적용되었다.](https://prod-files-secure.s3.us-west-2.amazonaws.com/5598c818-b1e9-40a6-9c9b-e6cecaee414e/d4bb98d7-16f8-4592-94d7-f17cb83a1922/Untitled.png)

정상 적용되었다.

# 5. 용어 정리

- Git: 버전 관리 시스템
- GitHub: Git으로 관리하는 프로젝트를 올려둘 수 있는 사이트
- GUI: 그래픽 유저 인터페이스 (마우스 클릭 등으로 사용)
- CLI: 커맨드 라인 인터페이스 (명령어를 입력해서 사용)
- Git Bash: Git을 CLI 방식으로 사용하는 환경
- commit: 버전 관리를 통해 생성된 파일, 혹은 그 행위
- log: 지금까지의 커밋을 모두 확인
- checkout: 원하는 지점으로 파일(커밋) 변경 가능
- 로컬 저장소: Git으로 버전 관리하는 내 컴퓨터 내의 폴더
- 원격 저장소: GitHub에서 협업하는 공간 (폴더)
- repository: 저장소
- push: 로컬 저장소의 커밋을 원격 저장소에 올리는 것
- pull: 원격 저장소의 커밋을 로컬 저장소에 내려받는 것