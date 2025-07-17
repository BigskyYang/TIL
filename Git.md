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


## Git revert & reset