## git 명령어들을 정리해 본다.

### bash

```bash
# 새로운 Git 저장소 초기화 후 .git 디렉터리 생성
git init

# 현재 브랜치 목록 확인
git branch

# 현재 브랜치에서 'develop'이라는 새 브랜치 생성
git branch develop

# 'develop' 브랜치로 전환
git checkout develop

# 'test'라는 새 브랜치를 생성하고 전환
git switch -c test

# 'main' 브랜치로 전환
git switch main

# text.txt 파일에 "Hello, World!" 문자열 추가, 파일이 없으면 파일 생성 후 저장
echo "Hello, World!" >> text.txt

# 현재 작업 디렉터리의 상태를 확인
git status

# text.txt 파일을 스테이징 영역에 추가
git add text.txt

# 현재 디렉터리의 모든 변경 사항을 스테이징 영역에 추가
git add .

# "first commit" 메시지로 커밋 생성
git commit -m "first commit" # 커밋 타입은 편의상 생략

# 원격 저장소에 변경 사항을 푸시
git push

# 원격 저장소 추가
git remote add origin <원격 저장소 URL>

# 지정한 원격 저장소와 브랜치에 변경 사항을 푸시
git push <원격저장소명> <브랜치명>

# 지정한 원격 저장소와 브랜치를 기본으로 설정하여 푸시
git push -u <원격저장소명> <브랜치명>

# 원격 저장소의 변경 사항을 가져옴
git pull

# 전체 히스토리를 간략히 그래프로 표시
git log --all --decorate --oneline --graph

# text.txt 파일을 원래 상태로 복원
git restore text.txt

# text.txt 파일을 원래 상태로 복원 (스테이징 전)
git checkout -- text.txt

# 스테이징된 text.txt 파일의 변경사항 취소
git restore --staged text.txt

# 스테이징된 text.txt 파일의 변경 사항 취소
git reset text.txt

# 'test' 브랜치 삭제
git branch -D test

# 삭제한 브랜치를 커밋 해시값으로 복원
git checkout -b <삭제한 브랜치명> <커밋 해시값>

# 원격 저장소를 추가하거나 기존 원격 저장소를 조회
git remote

# 원격 저장소에서 최신 변경 사항을 가져오지만, 현재 브랜치에 병합하지 않음
git fetch

# 원격 저장소에서 최신 변경 사항을 가져오고, 현재 브랜치에 병합
git pull # fetch와는 병합 유무의 차이

# 지정한 커밋으로 이동 (지정 커밋 이후의 작업 이력 초기화)
git reset

# 지정한 커밋의 내용으로 새로운 커밋 생성(작업 이력 보존)
git revert

# 현재 브랜치의 이름을 'main'으로 이름 변경
git branch -M main

# 새로운 저장소를 초기화할 때 기본 브랜치 이름을 'main'으로 설정
git config --global init.defaultBranch main

# 가장 최근 커밋의 메시지를 "새로운 커밋 메시지"로 수정
git commit --amend -m "New Commit Message"

#  이미 추적 중인 모든 파일의 변경 사항을 자동으로 스테이징하고 커밋 메시지와 함께 커밋
git commit -am "Commit Message"
```