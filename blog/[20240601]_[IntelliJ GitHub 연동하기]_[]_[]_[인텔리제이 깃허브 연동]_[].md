# IntelliJ와 GitHub 연동

## 인텔리제이와 깃허브 연동을 다시 한번 복습 겸 자바 프로젝트와 리포지토리를 새롭게 하나 생성 후 연동해 보았다.

## 1) 인텔리제이로 자바 프로젝트 생성

- 설명: 아무렇게나 생성하면 된다.

![1.png](img/intellij_github/1.png)

## 2) GitHub Repository 생성 후 주소 복사

- 설명: 깃허브 리포지토리를 생성 후 주소를 복사해온다.

![2.png](img/intellij_github/2.png)

## 3) Git 원격 관리

- 설명: 상단 메뉴의 Git에서 원격 관리… 를 눌러준다.

![3.png](img/intellij_github/3.png)

## 4) 원격 정의

- 설명: +를 누른 후 URL 부분에 복사한 주소를 붙여넣은 후 확인을 누른다.

![4.png](img/intellij_github/4.png)

## 5) .gitignore

- 설명: 프로젝트 창에서 .gitignore 파일에 Add Template… 를 누른다.
    - 보충 설명: .gitignore는 무시할 내용을 넣는다. 순수한 소스 코드를 제외하고는 다 제외한다.
        - 보충 설명: 만약 Add Templete이  안 보이면 플러그인에서 .ignore를 설치한다.

![5.png](img/intellij_github/5.png)

## 6) Add Template

- 설명: gradle, java, jetbrains + all 3가지를 추가 후 Generate를 누른다.
    - 보충 설명: 옵션으로 Visual Studio Code도 추가해도 된다.
    - 보충 설명: Java, Gradle은 두 개가 나오는데, 하나만 선택하면 된다.

![6.png](img/intellij_github/6.png)

## 7) .gitignore 파일에 내용 추가하기

- 설명: .gitignore에 제외할 파일들을 추가한다.
    - 보충 설명: 간단하게 src 폴더에 있지 않으면 다 추가한다.
    - 보충 설명: 이번의 경우 .idea/ 와 java-learn.iml을 추가했다.
    - 보충 설명: 파일 내에 넣는 위치(라인)는 관계없다.

![7-1.png./img/intellij_github/7-1.png)

![7-2.png./img/intellij_github/7-2.png)

## 8) 추적된 파일 제외

- 설명: 터미널에 git rm -r --cached . 를 입력한다.
    - 보충 설명: 오류가 발생했으니 아래의 8-1번과 같이 코드를 입력한다.

![8.png](img/intellij_github/8.png)

```bash
git rm -r --cached .
```

## 8-1) 오류 났을 때

- 설명: 터미널에 git rm -rf --cached . 를 입력한다.
    - 보충 설명: r뒤에 f를 붙였다.

![8-1.png./img/intellij_github/8-1.png)

```bash
git rm -rf --cached .
```

## 9) 브랜치 바꾸기

- 설명: Git 기본 브랜치는 master인데, GitHub에 연동할 것이기에 main으로 브랜치를 바꾼다.
    - 보충 설명: Git에선 Master란 브랜치가 default고, Github는 Master 대신 Main이 default다.

![9.png](img/intellij_github/9.png)

```bash
git branch -M main
```

## 9-1) master브랜치로 바꾸기

- 설명: 9번처럼 main 브랜치로 하지 않으면 코드가 master 브랜치에 올라간다.
    - 보충 설명: main 브랜치에서는 볼 수 없기에 기본 브랜치를 변경해준다.
    - 보충 설명: Settings → General → Default branch 에서 변경

![9-1.png./img/intellij_github/9-1.png)

## 10) 커밋 및 푸시

- 설명: 이후 .gitignore 파일과 기타 소스 코드 파일을 커밋 후 푸시한다.
    - 보충 설명: 커밋하는 사진을 못 찍었다… 아래는 깃허브 리포지토리 페이지 결과 사진

![10.png]/img/intellij_github/10.png)

## 11) 파일 명 수정

- 설명: 기존에 있던 Main 파일을 OnBoarding으로 이름을 바꾸었다.

![11.png]/img/intellij_github/11.png)

## 12) 커밋 및 푸시

- 설명: OnBoarding 파일 수정한 내용을 커밋 후 푸시한다.

![12.png]/img/intellij_github/12.png)

## 13) 커밋 결과 확인

- 설명: 잘 되어 있다.

![13.png]/img/intellij_github/13.png)

## 14) README.md 파일

- 설명: 리포지토리에서 직접 리드미 파일을 생성 후 수정까지 해본다.

![14.png]/img/intellij_github/14.png)

## 15) 리드미 파일 가져오기

- 설명: Git에서 페치를 한 후 풀… 까지 누른다.
    - 보충 설명: 페치 → 풀 순서

![15.png]/img/intellij_github/15.png)

## 16) 리드미 파일 수정

- 설명: 리드미 파일을 수정해본다.
    - 보충 설명: 인텔리제이로 작업

![16.png]/img/intellij_github/16.png)

## 17) 변경사항 커밋

- 설명: 리드미 파일 수정한 거 커밋

![17.png]/img/intellij_github/17.png)

## 18) 결과 확인

- 설명: 리포지토리에 변경 사항이 잘 커밋되어 있는 것을 확인할 수 있다.

![18.png]/img/intellij_github/18.png)