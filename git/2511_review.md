# Shell과 Vim commands

## Shell

운영체제의 커널과 사용자를 이어주는 **소프트웨어**

- 윈도우의 파일탐색기와 같은 역할
- 여러 쉘 중 BASH(Bourne Again Shell)을 다양한 운영체제에서 기본 쉘로 채택하여 사용

### Shell Command

- pwd: 현재 위치 조회
- ls: 현재 위치의 파일 및 디렉토리 조회
- cd: 위치 이동
- mkdir: 새 디렉토리 생성
- touch: 새 파일 생성
- mv: 이동 + 이름 변경
- cp: 복사
- rm: 삭제
- cat: 파일 내용 조회

## Vim

CLI 기반의 파일 편집기 중 하나로, vi의 확장판

- 모드 기반의 마우스 입력 대체

### 주요 Vim Command

- i - insert mode
- ESC - back to normal mode
- :q - quit
- :wq - write and quit


# Git(distributed Version Control System)

## Git Basic

### Git

분산형 버전 관리 시스템

- 특징
    - 단순한 구조와 빠른 속도
    - 분산형 저장소 지원
    - 비선형적 개발 가능
- 장점
    - 동시작업이 가능해 생산성 증가
    - 수정 내용이 commit 단위로 관리되어, 원하는 시점으로 checkout 가능
    - 새로운 기능을 추가할 때 Branch를 분리하고 새 작업이 성공적으로 완료되면 merge하여 반영
    - 인터넷이 연결되지 않아도 사용 가능

<aside>
💡

**Git ≠ Github**

**Git**은 version control **system**이며, **Github**는 open source repo **service**

서비스는 다른 것으로 대체가 가능하다!

- Github
- Gitlab: 사설 저장소 개설 기능을 제공하며, 금융권이나 보안이 중요한 업체에서 주로 사용
- Bitbucket: 다른 팀과 협업을 할 때 유용한 기능이 많음
</aside>

**Git Local and Remote Repository**
![Git Local and Remote Repository](C:\Users\lucia\Documents\dev\TIL\images\tempFileForShare_20251113-215001.jpg)

- Local (개인 PC)
    - Working Directory: 작업 공간
    - Staging Area: 저장소에 저장하려는 모든 변경 사항을 저장해두는 공간
    - Local Repository: 개인 PC 내 저장소
- Remote (공유 공간)
    - Remote Repository: GitHub 내 저장소

**실행 순서**

1. `git clone` + Github url
2. 파일 생성 및 작업 (`touch` → `vi` )
3. `git add` + 작업한 파일명
4. `git commit` → commit 제목(구 or 절 형태) 기록, 제목 앞에 prefix 반드시 입력
5. `git push origin main` : 작업 완료 후, github로 작업 기록 push → github에서 파일 생성한 이후~ 작업한 이력을 볼 수 있음

**Prefix type**
- feat: 기능 개발 관련
- fix: 오류 개선 또는 버그 패치
- docs: 문서화 작업
- test: test 관련
- conf: 환경설정 관련
- build: 빌드 작업 관련
- ci: continuous Integration 관련
- chore: 패키지 매니저, 스크립트 등
- style: 코드 포매팅 관련

## Git Branch

### Branch

**분기점**을 생성하여 **독립적**으로 코드를 변경할 수 있도록 도와주는 모델로, 작업을 이전 작업과 분리하여 할 수 있는 또 다른 공간

**실행 순서**

1. `git branch {branch name}` : branch 생성
2. `git switch {branch name}` : 기본 branch(main)에서 새 branch로 이동
3. 이동한 branch 내에서 필요한 작업 수행 후 `git add` , `git push
4. `git switch main` : 작업이 완료되면, 기본 branch로 돌아옴
5. `git merge {branch name}` : 기본 branch로 작업한 파일 이동(합병)
6. `git branch -D {branch name}` : 합병 후 branch 삭제
