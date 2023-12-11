- OSS 교과목 내용(Git & GitHub)의 정리
1. 임시저장 stash 개요
(1) 작업 영역과 스테이지 영역을 이전 커밋으로 복원
stash 개요와 필요성
-한 브랜치에서 작업을 하다 커밋 이전에 다른 브랜치로 이동하려면 checkout이나 switch가 되지 않는다
이 경우 명령 stash 이전 커밋 상태로 되돌리고 현재까지의 작업을 임시저장소인 ㅇㅁㄴtash에 저장할 수 있음.
즉 명령 stash로 작업 영역(working directory)과 스테이지 영역(stage area)을 스택구조에 stash에 임시로 저장함. 명령 stash와 stash save로 작업 영역의 modified인 파일과 스테이지 영역에 있는 파일들을 임시 보관할 수 있다.ㅇㅁㄴ
예)주요 명령
$git stashDSADAS
$git stash -m '임시저장 메시지'ㅇㄴㅁ
$git stash saveDASDAS
$git stash save '임시저장 메시지'
깃 설정 6가지
$ git config --global user.name suminying - 사용자 이름
$ git config --global user.email usm403@naver.com - 사용자 전자메일
$ git config --global core.autocrlf true - 줄바꿈 자동변환
$ git config --global core.safecrlf false - 줄바꿈 안전 설정
$ git config --global core.editor 'code --wait' - 기본 편집기 설정
$ git config --global init.defaultBranch main - 기본 브랜치 이름

저장소 생성
$ git init - 현재 티렉토리를 git repository로 만들기 위해서 사용
$ git init basic - 현재 폴더 하부에 폴더 basic을 생성하고 git repository로 만들기 위해서 사용

커밋
$ git commit - 커밋 메시지를 입력할 기본 편집기 실행됨
$ git commit -m 'message' - 커밋 메시지를 직접 입력
$ git commit -a -m 'message' - 추가와 커밋을 함께 실행

로그
$ git log 로그 이력 정보를 표시
$ git log --oneline - 로그 이력을 한 줄로 표시
$ git log [--patch|-p] - 로그 이력과 함께 파일의 변화

파일 비교 diff
$ git diff - 스테이징 영역 기준으로 작업 디렉토리 파일 비교
$ git diff --staged HEAD - 깃 저장소 기준으로 스테이징 영역 파일 비교
$ git diff HEAD - 깃 저장소 기준으로 작업 디렉토리 파일 비교 git diff HEAD^HEAD - 커밋 간의 파일 비교

파일 삭제 rm과 복원 restore
$ rm f - 디렉토리에서 파일 삭제
$ git rm f - 작업 디렉토리와 스테이징 영역에서 파일 삭제
$ git rm --cached f - 스테이징 영역에서만 파일 삭제
$ git restore f - 스테이징 영역의 상태를 작업 디렉토리에 복원
$ git restore --staged f - 스테이징 영역에 복원
$ git restore --source=HEAD --worktree f - 깃 저장소 상태를 작업 디렉토리에 복원
$ git restore --source=HEAD --staged --worktree f - 깃 저장소 상태를 스테이징 영역과 작업 디렉토리에 함께 복원

브랜치 개요와 관리
$ git branch - 저장소 목록 보기
$ git branch - 저장소 목록 보기
$ git checkout -b - 저장소 생성만
$ git switch -c - 저장소 생성하고 이동
$ git branch -d branch-name - 저장소 삭제
$ git branch -o branch-name - 저장소 삭제, 강제 삭제

원격 저장소
$ git clone https://github.com/ai7dnn/repo-sync.git - 원격 저장소 복제
$ git pull origin main - 원격 저장소 수정 사항 pull로 지역 저장소로 가져오기
$ git fetch origin main - 원격 저장소 수정 사항 fetch로 지역 저장소로 가져와 병합하기
$ git push origin main - 지역 저장소 수정 사항 push로 원격 저장소 보내기

브랜치 병합
$ git merge hotfix - 기준 브랜치에서 hotfix 브랜치 병합
$ git merge --no-ff hotfix - 무조건 3-way 병합 수행
$ git merge --ff-only hotfix - fast-forward인 경우에만 병합 진행
$ git merge --squash hotfix - 현재 브랜치에서 커밋 하나만 생성해서 병합

버전 되돌리기
$ git reset --hard ORIG HEAD - 이전에 수행한 reset을 바로 취소하는 명령
