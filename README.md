# 프로젝트 기반 VR 콘텐츠 개발과정 - 12기

<!-- ## 기획 팀 빌딩

|팀명|프로젝트명|플랫폼|팀원|
|---|---|---|---|
|Mapper|VR Chat Map 제작|VR|김상연, 김상윤, 김태완|
|Grovekeeper|VR 펫 키우기|VR|고민혁, 이시훈, 정수지|
|Future Frame|muu|VR|이재승, 유예찬, 신현지, 박동현|
|Blood Moon|Walking Zombie|VR|이채환, 이찬우, 박채린|

## 기획 산출물

- 기획서(최종)
- UI 구성도
- 시스템 구성도(Flow)
- 스토리보드
- 상세 기능 목록(엑셀, 구글 시트)

## 기획 발표

- 일자 : 2023년 1월 5일
- 시간 : 오전 09:30 부터

## Git 수업

### 복습 문제

1. 새로운 리포지토리 생성 - 별도의 폴더를 생성한 후 리포지토리 초기화 - git init
2. 3개의 파일을 생성(텍스트 파일)
3. 1번째 커밋
4. 1개의 파일 삭제한 후 커밋
5. 1개의 파일에 내용을 추가(변경한 후)
6. 커밋
7. 롤백 실습(1번째 커밋으로 롤백)
8. 브랜치 생성
9. 생성한 브랜치로 체크아웃
10. 해당 브랜치에서 파일내용 수정
11. 커밋
12. master 브랜치로 체크아웃
13. 동일한 파일 내용 수정(충돌 발생을 위한)
14. 수정 내용 커밋
15. master 브랜치로 병합 시도 -> 충돌 발생
16. 충돌 해결 (수정) 후 커밋
17. master 브랜치로 병합 완료


### 깃 브랜치 전략
### Git Flow

![](git-flow.png)

- 작업 시작하기 전 깃 작업

```shell
# 로컬 조장소가 develop 브랜치인지 확인
git branch

# 만약 develop 브랜치가 아닌경우 develop 브랜치로 체크아웃
git checkout develop

# 원격 저장소의 develop 브랜치에서 가져오기(Pull)
git pull origin develop

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 정상적으로 pull이 완료된 후 자신의 개발 브랜치로 체크아웃
git checkout dev/LJH

# 로컬 develop 저장소의 변경사항을 자신의 개발 브랜치로 Merge 한다.
git merge develop

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 정상적으로 병합이 완료된 후 작업을 진행한다.

```

- 작업 종료 후 깃 작업

```shell
# 자신의 개발 브랜치의 작업내용을 모두 커밋한다.
git add .
git commit -m "작업 내용"

# 로컬 develop 브랜치로 체크아웃한다.
git checkout develop

# 자신의 개발 브랜치의 내용을 로컬 develop 브랜치로 병합(merge) 한다.
git merge dev/LJH

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 충돌을 해결하거나 정상적으로 병합이 완료된 경우 원격 develop 브랜치로 push 한다.
git push origin develop

# 만약 원격 리포지토리에 변경 사항이 있을 경우 먼저 Pull 한 후 Push 한다.
``` -->

---
## ML-Agents 설정

#### Python 3.8.13 버전 설치
아래 사이트에 접속한 후 3.8.13 버전 설치 파일 다운로드 후 설치 (3.9.16 버전도 성공함)

https://github.com/adang1345/PythonWindows

#### 파이토치 1.7.1 설치
터미널에서 다음 명령어를 통해 설치

```sh
pip3 install torch~=1.7.1 -f https://download.pytorch.org/whl/torch_stable.html
```

#### ML-Agents 파일 클론

```sh
git clone --branch release_20 https://github.com/Unity-Technologies/ml-agents.git
```

#### 파이썬 패키지 설치
설치 후 터미널에서 ml-agents 폴더안으로 이동한 후 다음 명령어를 차래대로 실행

```sh
pip3 install -e ml-agents-envs
pip3 install -e ml-agents
```

#### Google Protocal Buffer 다운그레이드

protobuf 패키지를 삭제한 후 3.20.* 버전을 설치한다.

```sh
pip3 uninstall protobuf
pip3 install protobuf==3.20.*
```
---

### 깃 브랜치 전략
### Git Flow

![](git-flow.png)

- 작업 시작하기 전 깃 작업

```shell
# 로컬 조장소가 develop 브랜치인지 확인
git branch

# 만약 develop 브랜치가 아닌경우 develop 브랜치로 체크아웃
git checkout develop

# 원격 저장소의 develop 브랜치에서 가져오기(Pull)
git pull origin develop

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 정상적으로 pull이 완료된 후 자신의 개발 브랜치로 체크아웃
git checkout dev/LJH

# 로컬 develop 저장소의 변경사항을 자신의 개발 브랜치로 Merge 한다.
git merge develop

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 정상적으로 병합이 완료된 후 작업을 진행한다.

```

- 작업 종료 후 깃 작업

```shell
# 자신의 개발 브랜치의 작업내용을 모두 커밋한다.
git add .
git commit -m "작업 내용"

# 로컬 develop 브랜치로 체크아웃한다.
git checkout develop

# 자신의 개발 브랜치의 내용을 로컬 develop 브랜치로 병합(merge) 한다.
git merge dev/LJH

# 충돌(Conflict)가 발생한 경우 해결한 후 Merge Commit 한다.
git add .
git commit -m "충돌해결 - 내용"

# 충돌을 해결하거나 정상적으로 병합이 완료된 경우 원격 develop 브랜치로 push 한다.
git push origin develop

# 만약 원격 리포지토리에 변경 사항이 있을 경우 먼저 Pull 한 후 Push 한다.
```