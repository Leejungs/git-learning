- OSS 교과목 내용(Git & GitHub)의 정리
1. 임시저장 stash 개요
(1) 작업 영역과 스테이지 영역을 이전 커밋으로 복원
stash 개요와 필요성
-한 브랜치에서 작업을 하다 커밋 이전에 다른 브랜치로 이동하려면 checkout이나 switch가 되지 않는다
이 경우 명령 stash 이전 커밋 상태로 되돌리고 현재까지의 작업을 임시저장소인 stash에 저장할 수 있음.
즉 명령 stash로 작업 영역(working directory)과 스테이지 영역(stage area)을 스택구조에 stash에 임시로 저장함. 명령 stash와 stash save로 작업 영역의 modified인 파일과 스테이지 영역에 있는 파일들을 임시 보관할 수 있다.
예)주요 명령
$git stash
$git stash -m '임시저장 메시지'
$git stash save
$git stash save '임시저장 메시지'
한줄 정리
-->현재의 작업영역과 스테이지 영역에 있는 파일들을 임시보관, 필요에 따라 메시지를 입력 할 수 있다.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
dsa
asd
