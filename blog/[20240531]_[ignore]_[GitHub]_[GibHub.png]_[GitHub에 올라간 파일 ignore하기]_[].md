오래전에 잠시 썼던 레포지토리로 테스트 차원에서 실행해봤다.

이 레포지토리는 예전에 프론트엔드를 배울 때 클론 코딩을 진행했던 레포지토리다.

.gitignore 파일 생성 전에 인텔리제이로 프로젝트를 열고 깃허브에 .idea를 올려놨다.

아래는 그 .idea를 깃허브 레포지토리에서 내리는 과정이다.

1. gitignore 파일 생성

![이그노어 파일 추가.png](img/github_ignore/1.png)

2. gitignore 파일에 제외할 내용 추가

![이그노어 내용 추가.png](img/github_ignore/2.png)

3. gitignore 파일 커밋 및 푸시
4. 터미널에 다음과 같이 타이핑

```powershell
git rm -rf --cached .
```
5. 모든 파일 선택 후 커밋 및 푸시
6. 결과

![결과.png](img/github_ignore/3..png)