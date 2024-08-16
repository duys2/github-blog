# Git Commit Convention

## 1. Commit Message Structure
###  기본적인 커밋 메시지 구조
    
제목 ([Type] Subject) | 본문 (Body) | 꼬리말 (Footer)
    
    각 파트는 **빈 줄**을 두어 구분한다.  
    제목은 필수이고, 나머지는 선택사항
### 작성 방법 (Command)
```bash
git commit -m "[Type] Subject" -m "Body" -m "Footer"
```

```bash
git commit -m "[Type] Subject

Body

Footer
"
```
## 2. Commit Type (Subject)
### 커밋의 타입 구성

‘[태그] 제목’으로 [] 뒤에만 공백을 넣는다.

| Tag Name | Description |
| --- | --- |
| Feat | 새로운 기능을 추가 |
| Add | 기존 내용 중 기능을 더 추가 |
| Fix | 버그 수정 |
| Design | CSS 등 사용자 UI 디자인 변경 |
| !BREAKING CHANGE | 커다란 API 변경의 경우 |
| !HOTFIX | 급하게 치명적인 버그를 고쳐야 하는 경우 |
| Style | 코드 스타일 혹은 포맷 변경, 세미콜론 누락, 코드 수정이 없는 경우 |
| Refactor | 프로덕션 코드 리팩토링 |
| Comment | 필요한 주석 추가 및 변경 |
| Docs | 문서 수정 |
| Test | 테스트 코드, 리펙토링 테스트 코드 추가, Production Code(실제로 사용하는 코드) 변경 없음 |
| Chore | 빌드 업무 수정, 패키지 매니저 수정, 패키지 관리자 구성 등 업데이트, Production Code 변경 없음, 그 외 자잘한 수정 |
| Rename | 파일 혹은 폴더 명을 수정하거나 옮기는 작업만인 경우 |
| Remove | 파일을 삭제하는 작업만 수행한 경우 |
| Backup | 백업하는 경우 |
| Init | 프로젝트 초기화 |
| WIP | 진행 중인 작업 |
| Build | 빌드 파일 수정 |
| Perf | 성능 개선(최적화) |

```
[Feat] navigation
[Fix] db
```

## 3. Subject
    제목은 50글자 이내로 작성한다.
    마침표 및 특수 기호는 사용하지 않는다.
    영문의 경우 첫 글자는 대문자로 작성한다.
    영문으로 작성하는 경우 동사(원형)을 가장 앞에 명령어로 작성한다.
    과거 시제는 사용하지 않는다.
    개조식 구문(간결하고 요점적)으로 작성한다.
    
    예시) Fixed → Fix
    

## 4. Body
    72글자 이내로 작성한다.
    최대한 상세히 작성한다. (코드 변경의 이유를 명확히 작성할수록 좋다)
    어떻게 변경했는지 보다 무엇을, 왜 변경했는지 작성한다.

## 5. Footer
    Issue Tracker ID 작성에 사용
    `유형: #이슈 번호` 형식으로 작성
    여러 개의 이슈 번호를 적을 때는 `쉼표(,)`로 구분한다.
    이슈 트래커 유형은 다음 중 하나를 사용한다.
        해결 관련
            - `Fixes`: 이슈 수정 중 (아직 해결되지 않은 경우)
            - `Resolves`: 이슈를 해결했을 때 사용
            - `Closes`: 종료
        참고 관련
            - `Ref`: 참고할 이슈가 있을 때 사용
            - `Related to`: 해당 커밋에 관련된 이슈번호 (아직 해결되지 않은 경우)
            - `See also`: 참고
    예시
        - `Fixes: #45`
        - `Closes #13, #24`