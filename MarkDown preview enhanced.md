MarkDown preview enhanced 설명
===================================

<!-- toc orderedList:0 -->

- [MarkDown preview enhanced 설명](#markdown-preview-enhanced-설명)
	- [기울이기](#기울이기)
	- [굵게](#굵게)
	- [인용문](#인용문)
	- [링크](#링크)
		- [주소가 그대로 보이는 링크](#주소가-그대로-보이는-링크)
		- [주소가 그대로 보이지 않는 링크](#주소가-그대로-보이지-않는-링크)
		- [MarkDown 이미지 삽입](#markdown-이미지-삽입)
	- [취소선](#취소선)
	- [가로선](#가로선)
	- [표그리기](#표그리기)
	- [다이어그램](#다이어그램)
	- [코드 삽입](#코드-삽입)
	- [code chunk](#code-chunk)
	- [들여쓰기](#들여쓰기)
	- [특수기능](#특수기능)
		- [toc](#toc)
		- [수학기호의 사용 TeX 문법](#수학기호의-사용-tex-문법)
	- [출력](#출력)

<!-- tocstop -->

  ## 기울이기
  *기울이기*

  ## 굵게
  **굵게**

  ## 인용문

  >이렇게 하면 인용문을 만들 수 있다고 하니 이 얼마나 좋은 기능입니까?

  ## 링크

   ### 주소가 그대로 보이는 링크
    <https://google.com>

   ### 주소가 그대로 보이지 않는 링크
    [구글](http://google.com)

   ### MarkDown 이미지 삽입
    * 단축키 : control + shift + i

  ## 취소선
  ~~취소선~~

  ## 가로선

  ---  


  :  마크다운(Markdown)은 일반 텍스트 문서의 양식을 편집하는 문법이다. README 파일이나 온라인 문서, 혹은 일반 텍스트 편집기로 문서 양식을 편집할 때 쓰인다. 마크다운을 이용해 작성된 문서는 쉽게 HTML 등 다른 문서형태로 변환이 가능하다.

  ## 표그리기

  x | y | z
  --|--|--
  과일|당근|사과

  ## 다이어그램
  [문법 정리](https://knsv.github.io/mermaid/#nodes-shapes)

  ```{mermaid}
  graph LR

  처음 ==> 중간
  중간 ==말도쓸수 있다규==> 끝
  중간 == 알겠음? ==> 끝_2

  ```



  ## 코드 삽입

  ```c
  #include <stdio.h>

  int main(){
    printf("hello world!");

    return 0;
  }
  ```

  ## code chunk
  * 기능
  컴파일을 해준값을 출력해준다.
  ```{python2.7 id:"iujflzeb"}
  print('hello world')
  ```

  ## 들여쓰기
   >띄어쓰기에 따라 들여쓰는 것도 가능하다.

  ## 특수기능

   ### toc
   * 사용법 :
    1. command + shift + p
    2. toc 검색
   * 기능 : 목록을 만들어준다


   ### 수학기호의 사용 TeX 문법
   [문법 정리](https://ko.wikipedia.org/wiki/%EC%9C%84%ED%82%A4%EB%B0%B1%EA%B3%BC:TeX_%EB%AC%B8%EB%B2%95)

   ## 출력
   * 출력형식 : HTML, pdf, ebook
   * 출력방법 : 마우스 우클릭 export to disk 클릭!


> HTML 문법도 적용할 수 있다
