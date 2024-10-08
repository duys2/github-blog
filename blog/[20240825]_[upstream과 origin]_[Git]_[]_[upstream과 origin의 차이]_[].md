# upstream과 origin

---

## 들어가며

    git을 공부하다보면 upstream과 origin이라는 용어를 마주할 수 있다.

    개인적으로 어렵고 좀 헷갈리는 부분이 있어 정리해본다.

## upstream과 origin의 차이

    먼저, origin은 어디일까? 필자가 팀장의 repository를 fork 해왔다고 상황을 가정해보자.

    이때 origin은 원류, 즉, 기준을 만들어낸 기원이므로 내 repository를 의미한다.

    그렇다면 upstream은 어디일까? 원류를 만들어낸 상류이므로 팀장의 repository를 의미한다.

## 정리

    근본이 되는 repository를 upstream이라고 부르고, 내가 fork해서 가져온 repository를 origin이라고 부른다.

    fork를 하지 않은 경우 upstream을 따로 설정하지는 않으나 설정한다고 해도 사실상 같은 저장소를 가리킨다.

# 결론

    origin: 일반적으로 변경 사항을 푸시하는 포크된 저장소
    upstream: 주요 프로젝트 개발이 진행되는 포크된 원본 저장소 (팀장의 저장소)

### 추가: remote와 origin의 차이

    remote: 모든 원격 저장소를 통칭하는 말
    origin: 처음 'clone'한 remote 저장소를 가리키는 특별한 이름 (내가 클론한 remote)

### 추가
    git clone [저장소 url] : 저장소 git 상태 유지해서 그대로 받아오기 (깃헙주소도 되고.. 폴더주소도 됩니다. .git폴더만 있으면)

    git remote -v : 현재 컴퓨터 git이 어떤 저장소와 연결됐는지 알려줌 (clone 받으면 origin이 할당되는데 clone 받은 곳과 연결됩니다.)
    
    git remote remove origin : 현재 컴퓨터 git과 연결된 origin 저장소와의 연결을 해제
    
    git remote add origin [저장소 url] : 현재 컴퓨터 git과 특정 저장소를 origin이라는 이름으로 연결합니다. 이름은 다른 것도 가능합니다.
    
    git push origin [브랜치명] : 현재 컴퓨터 git이 가리키고 있는 브랜치의 커밋과 origin으로 연결된 저장소의 브랜치를 동기화합니다. [쓰기만, 읽기는 push를 pull로 바꾸면 됩니다]
    
    git push --set-upstream origin [브랜치명] : 현재 컴퓨터 git이 가리키고 있는 브랜치에서 git push만 쳤을 때 기본 동기화 경로를 지정하고 동기화합니다.