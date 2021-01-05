# hwoo3303-s-git-note
git 용어 및 사용법 정리

1. 명령어
- git config                        : configuration 상태 확인
- git config --list                 : config 설정상태 확인
- git config --global -e            : config 설정 편집
- git config --global core.autocrlf : windows : true(\r\n, carriage-return), OSX : input(\n) -> 개행방식의 차이로 인한 설정 상이
- git config --global alias.st status : (git status -> git st)
- git config --h                    : 명령어 터미널로 확인(git홈페이지 reference에서도 확인가능)
- git status                        : 현재 디렉토리내부의 작업상태(commit, 수정 유무), (default long)
- git status -h                     : git status의 세부 옵션 확인
- git add fileName                  : (fileName)파일을 커밋 준비
- git rm --cached fileName          : 커밋준비된 (fileName)파일을 다시 stage에서 내림
- git init                          : git 초기화
- git add *                         : 현재 디렉토리의 모든 파일 staging
- git add .                         : stage에 있지만 현재 디렉토리에서 삭제된 파일의 삭제상태를 적용하여 staging
- echo *.log > .gitignore           : .log확장자 파일들을 git stage에 추가 하고싶지 않을 때
- rm -rf .git                       : git 삭제
- git diff                          : 파일 변경사항 확인
- git diff --staged                 : 파일 변경사항 상세(staging area) 확인
- git diff -h                       : git diff의 세부 옵션 확인

2. SourceTree 사용법
- Create Remote Repository : 서버에 repository 생성
- Create Local Repository  : 로컬에 repository 생성


3. 깃의 3가지 Workflow(작업환경)
Local
- working directory : 작업중인 디렉토리
  - untracked : 새로 만들어진 파일 or 기존에 존재하던 프로젝트에서 깃을 초기화하면(깃이 파일의 정보를 인지 못할경우)
  - tracked : 깃이 이미 알고있는, 깃이 트레킹하고있는 파일
	  - modified : 이전 버전과 비교하여 수정된점이 있는 파일(해당 파일만 staging area로 옮길 수 있음)
	  - unmodified : 이전 버전과 비교하여 수정된점이 없는 파일
- staging area : 작업 후 버전 히스토리에 저장할 준비가 되어있는 파일
- git directory : 버전의 히스토리를 가지고있음(git repository라고도 불림)

4. 기타 정리
- Remote : Server Repository
- 각각의 커밋에는 스냅샷된정보가 담겨져있음(고유의 헤시코드가 부여됨) : 버전정보 참조가능(ex) message, author, date/time)
- diff관련
  - [difftool "vscode"]
	cmd = code --wait --diff $LOCAL $REMOTE	// code 다음에 터미널에서 대기, Local과 Remote를 비교
git difftool : .gitconfig에 설정한 에디터를 실행
git difftool --staged : .gitconfig에 설정한 에디터를 실행하여 stage 확인

