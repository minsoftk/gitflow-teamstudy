# 김효식, 김민성, 송진영의 학습기록

**2021.09.30~2021.10.01**

## 혼자 하는 git flow process - 김효식
1. 생성한 레포지토리를 `git clone` 받습니다.
2. 해당 디렉토리로 이동하여 `git flow init`명령어로 `git flow`를 시작합니다.
- 특이사항이 없다면 브랜치명을 기본값으로 유지합니다.
3. `git flow feature start feature명`으로 새로운 `feature`를 생성합니다.
4. 작업을 하고, `add, commit`을 하고, `git flow feature finish feature명`으로 `feature`를 종료합니다.
5. `git flow release start v버전명`으로 릴리즈 브랜치를 생성합니다.
6. 해당 작업이 끝나면 `git flow release finish v버전명`으로 릴리즈를 종료합니다.
7. `develop`브랜치와 `main`브랜치의 내용을 각각 `remote`에 `push`합니다.
8. 생성한 태그도 `git push --tags`로 올려줍니다.

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

### Commit 수정하기
최신의 커밋만을 수정을 권고한다. 이전의 커밋은 역사관점에서 바꾸는 것은 아닌 것 같다.
rebase는 브랜치위 잡은 시점을 옮겨주는 것. interactive하게 commit을 바꿔주는 기능도있다. 하지만 배우지 않을 것. 관점과 맞지 않기 때문에.

* `git commit --amend` : 최신 commit 수정

* commit은 자주하고 push는 신중하게 해라.

#### Reset(최악! 절대 쓰지 마라)

```
git reset --hard HEAD~3
git push -f origin <branch>
```
* 직전 3개의 commit을 삭제한 후, remote에 강제 push


Revert

* 잘못만들었다는 사과문을 만들어준다. Reset 같은 경우에는 좀비가 되어버려서 계속 생성이 된다.
