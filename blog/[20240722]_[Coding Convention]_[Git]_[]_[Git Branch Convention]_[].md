# Git Branch Convention
---
## 1. Branch Structure
### Branch 구조 (Serve Branch만 해당)
    Branch Type/Issue 번호 - Issue 명(기능 명)
## 2. Branch Type
### 브랜치 전략: Git Flow
### Main Branch
    main(master) : 배포 가능한 상태의 결과물, release 타겟
    develop : 구현한 기능을 병합하기 위한 branch, 통합 폴더의 기능
### Serve Branch
    feature : 새로운 기능을 개발할 때 기능별 branch를 만들어 작업
    release : 배포 하기 전 내용을 QA(품질 검사)하기 위한 브랜치, main과 devlop에 병합
    hotfix : release 이후 버그가 발생 시 main(master)에서 분기 후 수정, main과 devlop에 병합
```
feature/5-login
release-1.1
hotfix-1
```
## 3. Merge시 유의사항
    PR은 GitHub를 통해 수락
    PR 전 develop에서 먼저 merge 받아와 최신화 할 것 (충돌 해결)