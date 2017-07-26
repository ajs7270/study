 # Git

<!-- toc orderedList:0 depthFrom:1 depthTo:6 -->

* [Git](#git)
  * [Git의 개념](#git의-개념)
  * [기본 사용법](#기본-사용법)
    * [레포지토리 관리 시작](#레포지토리-관리-시작)
    * [사용자 설정](#사용자-설정)
    * [레포지토리 상태 확인](#레포지토리-상태-확인)
    * [수정 or 새로운 파일 추가](#수정-or-새로운-파일-추가)
    * [커밋](#커밋)
  * [고급 사용법](#고급-사용법)
    * [원격 저장소 확인](#원격-저장소-확인)
    * [저장소의 log 내역 확인](#저장소의-log-내역-확인)
    * [커밋 시 수정내역 확인](#커밋-시-수정내역-확인)
    * [소스코드 라인별 커밋 및 수정한 사람 확인](#소스코드-라인별-커밋-및-수정한-사람-확인)
    * [브랜치](#브랜치)
    * [커밋 관리](#커밋-관리)

<!-- tocstop -->

---

 ## Git의 개념

 - 분산 버전 관리 시스템
 ![branching-illustration@2x](http://i.imgur.com/lH5j8w8.png)

 - 파일의 상태
 ![lifecycle](http://i.imgur.com/fFY8CuP.png)

 ---

 ## 기본 사용법

 ### 레포지토리 관리 시작

 - 현재 디렉토리를 git 으로 관리하겠다고 선언한다.

 ```bash
  git init
 ```
 ![스크린샷, 2017-07-22 18-44-13](http://i.imgur.com/0geV6DJ.png)


 > - mkdir 폴더명
    ->  폴더명으로 폴더를 생성

>  - cd 폴더명
    -> 해항 폴더로 현재 디렉토리를 이동

 ### 사용자 설정
- 이 레포지토리를 사용하는 사용자의 이메일과 이름을 저장한다.

```bash
  git config --local user.email "이메일 주소"
  git config --local user.name "이름"
```

![스크린샷, 2017-07-22 19-00-05](http://i.imgur.com/G20vKPC.png)

 ### 레포지토리 상태 확인

- 현재 레포지토리의 상황을 볼 수 있다.

 ```bash
  git status
 ```
 ![스크린샷, 2017-07-22 18-46-55](http://i.imgur.com/fGvrEgb.png)


 > - touch 파일명
    -> 파일명으로 파일 생성

 > - ls
    -> 현재 디렉토리의 파일 및 폴더 확인  

  ### 수정 or 새로운 파일 추가
  - commit 을 하기 위해 수정하거나 새롭게 생성한 파일을 추가한다.

  ![스크린샷, 2017-07-22 18-56-31](http://i.imgur.com/aMNiXFJ.png)

  ### 커밋
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

---

  ## 고급 사용법

  ### 원격 저장소 확인
   * 현재 내 git 저장소와 연결되어 있는 원격 저장소를 확인한다.

   ```bash
      git remote -v
   ```

   ![스크린샷, 2017-07-22 19-12-54](http://i.imgur.com/e3xITsu.png)


   ### 저장소의 log 내역 확인
   * 현재 저장소의 log 내역을 보여준다. --graph와 --decorate 는 예쁘게 보기위해 붙여놓은 것이니 생략해도 된다.

  ```bash
    git log --graph --decorate
  ```

   ![스크린샷, 2017-07-22 19-16-22](http://i.imgur.com/fQA3h6F.png)

   ### 커밋 시 수정내역 확인

   * 현재 파일의 전체 수정내역 확인

   ```bash
    git diff

   ```
   ![스크린샷, 2017-07-22 20-17-38](http://i.imgur.com/Ykw5O3r.png)
   ![스크린샷, 2017-07-22 20-17-17](http://i.imgur.com/A1LowM6.png)

   > 빠진줄을 -로 (빨간색), 추가된 줄은 +로(초록색)으로 표시된다.

   * 현재 상황에서 커밋 시 수정되는 내용 확인

   ```bash
    git diff --cached

   ```

   ![스크린샷, 2017-07-22 20-24-35](http://i.imgur.com/XYtvo2f.png)

   >git add 를 하기 전에는 수정사항이 나오지 않았지만, add를 한 이후에 수정사항이 나온 것을 확인할 수 있다.

   ### 소스코드 라인별 커밋 및 수정한 사람 확인

   ```bash
      git blame 파일명

   ```

   ![스크린샷, 2017-07-22 20-27-39](http://i.imgur.com/AMJY0OD.png)
   ![스크린샷, 2017-07-22 20-27-10](http://i.imgur.com/rvfZvJu.png)

   >1열 : commit ID
   2열 : 수정한 사람
   3열 : 수정한 날짜
   4열 : 코드

   ### 원하는 부분만 add
   ```bash
   git add -p

   ```

   ![스크린샷, 2017-07-26 14-32-24](http://i.imgur.com/XkUBRg7.png)
   > 현재 파일을 수정한 부분 (빈칸삭제,  ### 원하는 부분만 add)

   ![스크린샷, 2017-07-26 14-35-39](http://i.imgur.com/YwO1Aex.png)
   > 여러가지 선택을 할 수 있는 경우가 나온다.
   > y = OK라는 뜻
   > n = NO라는 뜻
   > e = add 할 부분을 수정할 수 있음 -> diff 문법

   ![스크린샷, 2017-07-26 15-13-26](http://i.imgur.com/WiAKXtv.png)
   ![스크린샷, 2017-07-26 15-14-23](http://i.imgur.com/yhKDaF5.png)

   ### 브랜치
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


  ### 커밋 관리

  * 커밋 내용 확인

  ```bash
    git show HEAD

  ```

  ![스크린샷, 2017-07-22 20-37-51](http://i.imgur.com/Z7fZA4H.png)

  > 몇줄 추가 정도만 확인  (--stat 파라미터 추가)
  ![스크린샷, 2017-07-22 20-42-03](http://i.imgur.com/t7rmLWw.png)

  > HEAD : 현재 commit 위치
  > HEAD~0 : 현재 commit 위치
  > HEAD~1 : 첫번째 전 commit 위치
  > HEAD~2 : 두번째 전 commit 위치

  * 수정하고 싶은 부분만 정하기
  ```bash
    git rebase -i 지금부터 수정하고 싶은 위치의 HEAD

  ```
  ![스크린샷, 2017-07-26 15-28-44](http://i.imgur.com/lHFEKjh.png)
  ![스크린샷, 2017-07-26 15-31-37](http://i.imgur.com/rTCQK0C.png)
  > 노란색 부분 중 pick 인 부분은 고정된 부분
  > 내가 바꾸고 싶은 commit 은 e 또는 edit로 수정 한다.
