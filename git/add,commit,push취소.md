## git add 취소

git add .을 너무 자주써서, 단계별로 스테이징 단계에 구분없이 올리는 경우가 많아 취소 하는법 찾아봄.

`git reset HEAD [file]` : git add 취소 할 수 있음

* 파일 경로까지 다 작성해 줘야 삭제되는 것 같다. (~~.md만 작성시 status확인 하니 안됨.)

- git reset HEAD 로 `[file]` 없이 명령 하면, 모든 스테이징 상태의 

add 말고, commit, push 등도 취소할 수 있는데,

해당내용은 [블로그][https://gmlwjd9405.github.io/2018/05/25/git-add-cancle.html] 참고~



## git Commit 취소

`git reset HEAD^` : 가장 최근 커밋을 취소

`git reset HEAD~{number}` : number만큼의 commit을 순차적으로 취소







