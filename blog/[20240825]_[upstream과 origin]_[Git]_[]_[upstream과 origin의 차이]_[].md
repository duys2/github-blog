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