




 # Git
---
 ## Git 기본
 ### Git의 개념

 - 분산 버전 관리 시스템
 ![branching-illustration@2x](http://i.imgur.com/lH5j8w8.png)

 - 파일의 상태
 ![lifecycle](http://i.imgur.com/fFY8CuP.png)

 ### 기본 사용법

 #### 레포지토리 관리 시작

 - 현재 디렉토리를 git 으로 관리하겠다고 선언한다.

 ```bash
  git init
 ```
 ![스크린샷, 2017-07-22 18-44-13](http://i.imgur.com/0geV6DJ.png)


 > - mkdir 폴더명
    ->  폴더명으로 폴더를 생성

>  - cd 폴더명
    -> 해항 폴더로 현재 디렉토리를 이동

 #### 사용자 설정
- 이 레포지토리를 사용하는 사용자의 이메일과 이름을 저장한다.

```bash
  git config --local user.email "이메일 주소"
  git config --local user.name "이름"
```

![스크린샷, 2017-07-22 19-00-05](http://i.imgur.com/G20vKPC.png)

 #### 레포지토리 상태 확인

- 현재 레포지토리의 상황을 볼 수 있다.

 ```bash
  git status
 ```
 ![스크린샷, 2017-07-22 18-46-55](http://i.imgur.com/fGvrEgb.png)


 > - touch 파일명
    -> 파일명으로 파일 생성

 > - ls
    -> 현재 디렉토리의 파일 및 폴더 확인  

  #### 수정 or 새로운 파일 추가
  - commit 을 하기 위해 수정하거나 새롭게 생성한 파일을 추가한다.

  ![스크린샷, 2017-07-22 18-56-31](http://i.imgur.com/aMNiXFJ.png)

  #### 커밋
  - 수정한 내용을 commit 한다.

  ```bash
    git commit
  ```
  ![스크린샷, 2017-07-22 19-01-44](http://i.imgur.com/alPxF9b.png)
  ![스크린샷, 2017-07-22 19-04-24](http://i.imgur.com/FWk6Ags.png)

  >* vim 텍스트 입력 방법
  아무것도 안했을 때  : 기본모드
  i 눌렀을 때 : 끼워넣기 모드(텍스트 입력 가능)
  esc 눌렀을 때 : 기본모드

  > * vim 파일 저장 방법
  > 1) 기본 모드에서 :wq를 입력
  >![스크린샷, 2017-07-22 19-07-25](http://i.imgur.com/jupQwdm.png)

  ![스크린샷, 2017-07-22 19-08-12](http://i.imgur.com/iXhWKFL.png)


  ### 고급 사용법

  #### 원격 저장소 확인
   * 현재 내 git 저장소와 연결되어 있는 원격 저장소를 확인한다.

   ```bash
      git remote -v
   ```

   ![스크린샷, 2017-07-22 19-12-54](http://i.imgur.com/e3xITsu.png)


   #### 저장소의 log 내역 확인
   * 현재 저장소의 log 내역을 보여준다. --graph와 --decorate 는 예쁘게 보기위해 붙여놓은 것이니 생략해도 된다.

  ```bash
    git log --graph --decorate
  ```

   ![스크린샷, 2017-07-22 19-16-22](http://i.imgur.com/fQA3h6F.png)

   #### 커밋 시 수정내역 확인

   ```bash


   ```


   #### 브랜치
   * 현재 브랜치 확인

   ```bash
   git branch

   ```


  ![스크린샷, 2017-07-22 19-27-56](http://i.imgur.com/qwQ8ojZ.png)

  * 새로운 브랜치 생성

  ```bash
    git branch 브랜치이름

  ```
  ![스크린샷, 2017-07-22 19-29-47](http://i.imgur.com/gsO14I7.png)

  * 브렌치 이동

  ```bash
    git checkout 브랜치이름

  ```
  ![스크린샷, 2017-07-22 19-36-37](http://i.imgur.com/zmbFdVu.png)

  * 브랜치 삭제

  ```bash
    git branch -d 브랜치이름

  ```
 ![스크린샷, 2017-07-22 19-38-09](http://i.imgur.com/dZGbdsQ.png)


  #### 커밋 관리

  *
