# Start Camp Day 2
## Remote Repository
### 원격 저장소
코드와 버전 관리 이력을 온라인 상의 특정 위치에 저장하여 여러 개발자가 협업하고 코드를 공유할 수 있는 저장공간
ex. GitHub, GitLab, Bitbucket
### 로컬 & 원격 저장소
#### remote
```GitHub Repository <-- remote --> Local Repository```
- 로컬에서 작업한 커밋을 원격에 올리거나 `push`, 원격의 최신 커밋을 내 로컬로 가져오는 `pull`/`fetch` 역할
- `git remote` : 등록된 원격 저장소 이름 목록 보기
- `git remote -v` : 이름과 URL을 함께 자세히 보기
- `git remote add [이름] [URL]` : 새로운 원격 저장소 등록
- `git remote rename [old] [new]` : 원격 저장소 이름 변경
- `git remote rm [이름]` : 현재 로컬 저장소에 등록된 원격 저장소 삭제

#### push / pull & clone
```
GitHub Repository -- push -> Local Repository
GitHub Repository <-- pull or clone -- Local Repository
```
- `git push [이름] master/main` : 원격 저장소에 commit 목록을 업로드
- `git pull [이름] master/main` : 원격 저장소의 변경사항만을 받아옴(업데이트)
- `git clone [이름] master/main` : 원격 저장소 전체를 복제(다운로드)

| 명령어         | 역할           | 동작                                          | 병합 여부 | 주 사용 시점                  |
| ----------- | ------------ | ------------------------------------------- | ----- | ------------------------ |
| `clone` | 원격 저장소 복제    | 새로운 디렉터리에 원격 저장소의 전체 커밋·브랜치·파일을 내려받음        | 없음    | 로컬에 repo가 없을 때 최초 복제     |
| `fetch` | 원격 변경사항 가져오기 | 원격 저장소의 최신 커밋을 원격 추적 브랜치(`origin/*`)에만 업데이트 | 없음    | 로컬 브랜치에 영향 없이 확인만 할 때    |
| `pull`  | 가져오기 + 병합    | 내부적으로 `fetch` 후 현재 체크아웃된 브랜치에 자동 병합         | 자동 병합 | 원격 변경사항을 바로 내 브랜치에 반영할 때 |

#### gitignore
- Git이 관리하지 않을 파일이나 디렉터리를 지정하는 설정파일
- 보통 프로젝트 최상단에 두고, 아래 내용들을 적음
- 이미 git의 관리를 받은 이력이 있는 파일이나 디렉토리는 나중에 gitignore 작성해도 적용 안됨
- (git rm -- cached 명령어를 통해 git 캐시에서 삭제 필요)
- [운영체제, 프레임워크, 프로그래밍 언어 등 개발환경에 따라 gitignore 목록을 만들어주는 사이트] https://www.toptal.com/developers/gitignore/

## GitHub의 활용법
1. 프로젝트 협업
2. 개인 포트폴리오(TIL)

## README.md
- 프로젝트에 대한 설명, 사용 방법, 문서화된 정보 등을 포함하는 역할
- Markdown 형식으로 작성되며, 프로젝트에 대한 전반적인 이해와 활용 방법을 제공
- 소개, 설치 및 설정 방법, 사용예시, 라이선스정보, 기여방법 등을 포함
- 저장소 최상단에 위치해야 원격 저장소에서 올바르게 출력됨

## Git revert & reset
`git revert [commit 해쉬값]` : 특정 commit을 없었던 일로 만드는 작업
- 변경 사항을 안전하게 실행 취소할 수 있도록 도와주는 순방향 실행 취소 작업
- commit 기록에서 commit을 삭제하거나 분리하는 대신, 지정된 변경 사항을 반전시키는 새 commit을 생성
- git에서 기록이 손실되는 것을 방지하며 기록의 무결성과 협업의 신뢰성을 높임

`git reset [옵션] [commit 해쉬값]` : 특정 commit으로 되돌아가는 작업
`--soft` : 삭제된 commit의 기록을 staging area에 남김
`--mixed` : 삭제된 commit의 기록을 working directory에 남김(defalt)
`--hard` : 삭제된 commit의 기록을 남기지 않음

`git reflog` : HEAD가 이전에 가리켰던 모든 commit을 보여줌, reset의 --hard 옵션을 통해 지워진 commit도 조회하여 복구 가능