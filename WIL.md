# 김효식, 김민성, 송진영의 학습기록i

## 김민성
## 상황별 되돌리기
### 한가지 파일 수정 상태 되돌리기
checkout에는 2가지 기능이 있는데 현재는 restore, switch로 변경됐다. checkout으로도 사
용은 가능하다. `git add` 로 staged 된 파일을 되돌려야 하는 상황이 있다.

* `git checkout -- (해당 파일 이름)` : 한가지 파일에 대한 상태 되돌리기.

* `git checkout -- .` : 변경된 모든 파일에 대한 상태 되돌리기.

### add된 데이터 Unstaged 만들기
앞의 checkout을 쓰기 전에 add를 해버렸을 때, staged된 데이터를 Unstaged 되게 만들어주
는 방법도 있다.

* git reset HEAD (~~)

* git rm -rf {파일명} : unstaged까지 하고 파일을 삭제함.

