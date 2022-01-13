__Branch__

```
깃배쉬 실행

mkdir git-branch-practice

cd git-branch-practice

code .



VSCODE에서

git init (깃으로 관리하겠다)

git branch

git branch -r
```



master-1 master-2 master-3 생성한 뒤, git log --oneline을 입력해보면 마지막에 입력한 master-3에 HEAD와 master가 붙어있는 것을 알 수 있다.



------------------

__Branch__

__master branch__ : 상용을 의미. 언제든 세상에 공개 가능 

+ 장점
  + 독립공간을 가지므로 원본(master)에 대해 안전
  + 하나의 작업을 브랜치로 나누어 개발이 가능하므로 체계적인 개발이 가능
+ 단점
  + 단계적으로 개발을 하는데, 각 단계의 개발 수준이 맞지 않으면 Massed up

-----------------------------

12) __branch 생성__

```
git branch <이름>
```

13. __branch 이동__

```
git switch <이름>

*__git switch-c <이름>__ => 생성하고 이동까지
```

14. __branch 삭제__

```
git branch -d <이름> => merge 한 브랜치만 삭제
git branch -D <이름> => 강제 삭제
```

```
git log --oneline
git log --oneline --all
git log --oneline --all --graph
```

------------------------------

15. __merge(병합)__

+ merge의 3종류
  + fast-forward : ㅇ-ㅇ-M-ㅇ-L 일 경우, L을 지우고 ㅇ-ㅇ-ㅇ-ㅇ-M
  + 3-way merge
  + merge conflict

```
git merge <브랜치 이름>
```

현재의 HEAD가 있는 브랜치로 <브랜치 이름> 브랜치를 통합. 대부분은 MASTER에다 두고 <새로운 브랜치>를 적어서 합치는 경우가 많다.



merge conflict의 경우, 동시에 같은 파일을 다른 내용으로 바꾸고 merge 했을 때 발생한다.

(git status에서)

i => 편집 모드

esc => 명령 모드

:wq => 저장하고 quit



16) __되돌리기__

새로운 파일을 stage => unstage

```
git rm --cached <파일이름>
```

수정 후 stage => unstage로 바꾸는 것

```
git restore --staged <파일이름>
```

17. __마지막 commit에 stage된 수정사항 추가__

```
git commit --amend
```



__vim 간단 사용법__

+ 입력 모드(i)
  + 문서 편집 기능
+ 명령 모드( esc )
  + dd : 해당 줄 삭제
  + :wq : 저장 및 종료
  + w : write (저장)
  + q : quit(종료)
  + :q! : 강제 종료
  + q : quit
  + ! : 강제

18. __이전 commit으로 이동__

    ```
    git reset --soft/--mixed/hard <commit ID> # 여기서 commit ID란 c41641b같이 16진수
    ```

+ --soft

  돌아가려는 커밋으로 되돌아가고, 이후의 commit된 파일들을 staging area로 돌려놓음(commit하기 전 상태). 즉, 다시 커밋할 수 있는 상태가 됨

+ --mixed

  돌아가려는 커밋으로 되돌아가고, 이후의 commit된 파일들을 working directory로 돌려놓음 (add 하기 전 상태) 즉, unstage된 상태로 남아있음. 기본 값

+ --hard

  돌아가려는 커밋으로 되돌아가고, 이후의 commit된 파일들(tra) 단,  Untracked 파일은 Untrac

19. __이전 commit의 내용으로 추가 commit__

```
git revert <commit ID>
```



gitlab(github)에 repository를 만들고 local로 갖고 올때는 한 번 clone, 필요할때마다 변경사항 pull. 근데 남의꺼에다가 push하면 안돼요



local 폴더를 만들고 repository에 붙일 때는 init => remote(push 전) => add => commit => push. 필요시 pull. 