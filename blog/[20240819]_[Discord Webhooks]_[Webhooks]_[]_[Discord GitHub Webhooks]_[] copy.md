## Discord GitHub Webhook를 설정해 보자.

### 1. 채널 설정

    서버를 생성 후 채팅 채널의 설정을 들어간다.

![1.png](img/web_hook/1.png)

### 2. 연동하기

    연동 메뉴에서 웹후크를 클릭한다.

![2.png](img/web_hook/2.png)

### 3. URL 복사

    웹후크 생성 후 URL을 복사한다.

![3.png](img/web_hook/3.png)

### 4. GitHub와 연동하기

    웹후크를 연결할 깃허브 레포지토리에 접속한다.

    Settings → Webhooks → Add webhook

![4.png](img/web_hook/4.png)

### 5. 설정값 입력하기

    Payload URL에 복사한 URL을 붙여 넣는다.

    이때 맨 뒤에 /github를 추가로 적는다.

    Content type은 application/json으로 설정했다.

    아래에 Add webhook 버튼을 눌러 생성한다.

![5.png](img/web_hook/5.png)

### 6. 생성 결과 확인

    아래와 같이 초록색 체크 표시가 되었으면 성공적으로 진행된 거다.

![6.png](img/web_hook/6.png)

### 7. 커밋 푸시하기

    README.md 파일을 수정 후 Commit Push 한다.

```Bash
# [Docs] README.md 파일을 업데이트하고 커밋 메시지와 함께 변경 사항을 스테이징 및 커밋
git commit -am "[Docs] README.md Update"

# 커밋 내용을 origin 이라는 이름의 원격 저장소의 main 브랜치로 푸시
git push origin main
```

### 8. 실행 알림

    다음과 같이 디스코드 알림이 온다.

![8.png](img/web_hook/8.png)

### 9. 최종 결과 확인

    아래 사진처럼 정상 작동하는 모습을 볼 수 있다.

![9.png](img/web_hook/9.png)