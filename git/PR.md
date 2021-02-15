## 1. make branch

```jsx
# 자신이 생성할 branch를 생성한다.
$ git checkout -b ljs_20201221
Switched to a new branch 'ljs_20201221'

# 이제 2개의 브랜치가 존재한다.
$ git branch
* ljs_20201221
  master
```

## 2. code add , commit , push

수정한 코드 푸시를 위해 add commit push 작업 진행

***) push 진행시에 branch 이름을 명시해주어야 한다.**

## 3. Pull Requset

- push 완료 후 본인 계정의 github 저장소에 들어오면 **Compare & pull reqeust** 버튼이 활성화 되어 있다.
- 해당 버튼을 선택하여 메시지를 작성하고 PR을 생성한다.
- **(병합하려고 하는 브랜치 명을 확인하고 병합한다. ljs → dev로)**

<img width="804" alt="pr-image" src="https://user-images.githubusercontent.com/52526452/107897006-543ee280-6f7b-11eb-96bc-fa674c6138c9.png">


## 4. Merge Pull Request

PR을 받은 원본 저장소 관리자는 코드 변경내역을 확인하고 Merge 여부를 결정한다.

(충돌시 web editor로 수정이 가능)

## 5**. Merge 이후 동기화 및 branch 삭제**

- 원본 저장소에 Merge가 완료되면 로컬 코드와 원본 저장소의 코드를 동기화 한다.
- 작업하던 로컬의 branch를 삭제한다.

```jsx
# 코드 동기화
$ git pull dev 
# 브랜치 삭제
$ git branch -d ljs_20201221(브랜치 별명)
```