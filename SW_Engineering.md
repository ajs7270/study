 # 소프트웨어 엔지니어링

 ## 요구사항 분석

 * UseCase 기반의 요구사항(Requirement Analysis) 분석
 1. 유스케이스 모델링
 2. 기술서 작성
 3. 기능 비기능 분류
 4. 요구사항 명세서 작성

* UseCase - UseCase Diagram(그림)을 통해서 쉽게 알아볼 수 있게 하는 것
  * 사용자 기준에서 요구사항을 추출하는 것
  * 고객과 개발자는 표준화된 규칙을 가지고(UseCase) 시스템을 표현하고 고객과 개발자, 사용자의 관점의 간격을 조정하는 것을 UseCase를 이요하여 요구사항을 분석한다고 한다.
  * 요즈케이스 기반의 요구사항 분석은 UML을 이용해 모델링 한다.

* UML
  * 모델링하는 방법을 통일했다.
  * 모델링 : 어떤 현상을 이해하기 쉽게 표현하는 일
  ex) 모델하우스
  * UML 개요
  SW 개발이 복잡해지고 사용자 요구가 모호해지면서 모델링의 표준화 표기볍 필요성 대두
  -> 시스템에 대한 다양한 뷰(View) 제공
  * 가시화, 명세화, 구축, 문서화에 이점을 준다.


* UseCase Diagram
  * 구성요소 : System, Actor, Usecase Relationship
  * System - Usecase를 둘러싼 사각형의 틀을 그리고 안에 이름을 씀
  * Actor - 사람일수도 시스템일 수도 있다.
    * 식별 - 누가 기능을 제공하는지
  * Usecase - Actor에게 제공해야하는 기능의 집합, ~한다고 기술
    * 식별 - 엑터가 원하는 시스템 제공 기능은 무엇인가?

  * Relationship
    * 연관관계(Association) - 동등
      * 식별 - 엑터와 유즈케이스 사이의 상호작용이 존재하는가?
    * 의존관계(Dependency) -> 점선 화살표       
      * 포함관계(include) ex)로그인
        * 식별 - 이 유즈케이스를 실행하기위해 반드시 실 되어야 하는 유즈케이스가 존재하는가?
      * 확장관계(extend) ex)결제(카드, 현금 등)
        * 식별 - 이 유즈케이스를 실행함으로써 선택적으로 실행되는 유즈케이스가 있는가?
    * 일반화 관계(generalization) -> 실선 화살표
      * 식별 - 엑터 또는 유즈케이스가 구체화된 다른 여러 엑터나 유즈케이스를 가지고 있는가?

 ## 설계/구현

 * 설계 - 어떻게 구현할지를 결정
  **비기능적 요구사항에 의한 제약을 반영** 하고, 좋은 품질을 내려는 일반적인 이론에 충실하면서 시스템의 **기능적 요구사항을** 구현할 방법을 찾고 나타내기 위한 문제해결 과정 -> 코딩할 수 잇는 밑바탕을 만드는 것
  인터페이스, Database도
  * 절차
    1. 어떤것을 하드웨어로할지 소프트웨어로할지 결정
    2. 아키텍처를 구분(패터닝)한다.
    3. 서브시스템의 상세한 사항의 클래스 알고리즘 등을 설계(상세설계)
    4. 서브시스템들의 상호작용들을 정리
    5. 자료를 어떻게 저장할 것인지 정함
  * 구분
    * 상위설계 - 아키텍처 설계, 구성에 대한 설계 구성 컴포넌트간의 관계로 구성된 시스템의 전체 구조
    -> 형태를 구성
      1. 구조설계
      2. DB설계
      3. 인터페이스 설계 -> 서로 independent하게 구성
    * 하위설계 - 모듈설계
    -> 형태안에서 어떤일이 발생하는 지를 설계하는 것
      1. 컴포넌트 설계
      2. 자료구조 설계
      3. 알고리즘 설계
  * 용어
    * 컴포넌트(Conponent) - 명백한 역할을 가지고 있으며 독존할 수 잇는 소프트웨어 또는 하드웨어의 한 부분
    * 모듈(Module) - 프로그래밍언어 수준에서 정의된 컴포넌트
    * 시스템(System)
    * 서브 시스템(Subsystem)
 * 설계 방식
  * 프로세스 지향 설계 - C언어 같은 설계 -> 소규모에 적합
    - 시스템이 커질수록 제어 힘듬
  * 객체 지향 설계 - 절차가 아닌 문제를 중심으로 설계 -> 대규모에 적합
    - 결합도가 작기 때문에 시스템 변경이 용의

  * 설계 원리
    * 분할정복
    * 응집력을 증진
    * 결합력 감소
    * 높은 수준의 추상화(Abstraction) - 핵심적인 큰 그림을 그리는 것
    * 재사용성 증진
    * 이식성
    * 테스트 가능성
    * 방어적인 설계
    * 단계적 분해 추상화
    * 모듈화
* 구현 - 코딩하는 것
  * 구현의 성공은 설계에서 나온다.

 ### UML(Unified Modeling Language)
 -> 통합된 모델링 언어
 분석 -> 설계 -> 구현 -> 테스트라는 단계중
 * 복잡한 아이디어를 간결하고 정확하게 표현하는 표기법 -> 시스템 특성 표현 적합, 참여자 이해 쉬움(의사소통을 잘 해야한다.)
 * 표준화된 표기법을 알아야 함
 * 객체지향 소프트웨어를 모델링하는 통합된 언어이다.

 * 모델링
    * 모델링 - 모델을 만들기 위한 행위, 물리현상을 쉬운 형식으로 표현, 사물의 형태를 추상화하여 형상화 -> 개발자가 개발하기 전에 하는 모든 활동을 모델링이라고 한다.
    * 모델 - 모델링 활동의 결과물
    좋은모델 -> 표준화된 사용방법 사용, 고객과 사용자가 쉽게 이해, 엔지니어가 시스템에 대해 통찰력을 가질 수 있게
    * 모델링에 사용하는 언어를 모델링이라고 하고 UML을 모델링 언어라고 한다. -> 즉 모델링의 결과물을 표현하기 위한 언어이다.
    * UML만 알고있다면 프로젝트 이해관계자들 사이의 불일치를 해결할 수 있다.-> 개발시스템에 대한 다양한(View를 제공해준다.) -> 가시화, 명세화, 구축, 문서화

* 다이어그램 종류
  서로 변환이 가능함.
  * Usecase 다이어그램
  * 클래스 다이어그램
  * 패키지 다이어그램
  * sequence 다이어그램
* 구성요소
  * 사물
    * 추상적 개념으로 모델에서 가장 중요
    * Structural things
      * Class *
      * Interface
      * Communication
      * Use Case *
      * Active Class
      * Component
      * Node - 실행할 때 존재하는 물리적 요소
    * Behavioral Things
      * Interaction
    * Grouping Tings
      * Package
    * Annotation Things
      * Note
  * 관계 - 사물간 관계 표현
    * Dependency(의존)
      - 두 사물간의 의미적 관계로서 한 사물에 명세가 바뀌면 다른사물에 영향으 끼침 반대는 성립하지 않는다 **점선으로 구성**
    * Association(연관)
      - 구조적 관계로서 관계를 설명하기 위해 이름을 사용한다. 이름이 읽히기 원하는 방향으로 방향 삼각형을 표기한다.**실선으로 표현**
      - Multiiplicity(다중성)
        * 다중성은 정확히 하나(1), 제로 혹은 하나(0..1), 다수(0..\*), 그리고 하나 혹은 그이상(1..\*)등으로 표현할 수 있다.
      - 집합연관
        * has-a 관계(전체를 대표하는 클래스를 가르키는 마름모꼴로 표현)
    * Generalization(일반화)
      * 일반화된 사물을 가르키는 빈 화살표로 표현
    * Realization(실체화)
      * 점선 빈 화살표로 표현

  * 다이어그램 - 사물과 관계를 그래프로 표현
    * 정적 다이어그램
      - 클래스 다이어그램(Class Diagram)
      - 객체 다이어그램(Object Diagram)
    * 동적 다이어그램
      - 유즈케이스 다이어그램(Use Case Diagram)
        * 사용자 관점에서 보여주는 다이어그램
        * 시스템에 대한 시나리오의 집합
        * 이벤트의 흐름을 시작하는 객체가 액터이다.
        * 구성요소
          * Actor - 시스템 외부에서 시스템과 상호작용하는 것
          * Usecase - 시스템의 요구사항을 보여줌(동사로 표현)
          * System - 개발하고자 하는 목표 어플리케이션
          * Relationship - Actor와 Usecase사이의 의미있는 관계
            * association(연관) - 실선
            * include - 점선(\<\<include>>라고 표현)
            * extend - 점선(\<\<extend>>라고 표현)
            * generalization(일반화, 추상적으로 그룹핑) - 구체적인 케이스에서 추상적인 케이스로 **실선 화살표 표현**
        * 작성 순서
          1. Actor 식별
          2. Usecase 식별
          3. Relationship 식별
            * Association
            * include
            * extend
            * generalization
        * Usecase Discription 작성
      - 클래스 다이어그램 (Class Diagram)
        * 구성요소 - 3부분으로 나눔
          * Class Name(클래스 이름)
          * attribute(속성)
          * method(메서드)
        * 나타내는 법
          * 여러단어 :첫글자가 대문장인 camel표기법
          * UML 패키지 => 댑이달린 폴더
          * 경로 : "패키지 이름" :: "클래스 이름"
          * 속성 : camel표기법 (만약 값이 있으면 = "값"으로 넣어준다.)
          * Operation : camel 표기법
            * Operation Signiture
              * 파라미터 acceptClothes(c:String)
              * 반환값 turnOn():Boolean
          * 책임(responsibility) - 세번째 칸
          * 제약(constraint) - ({제약사항})
          * note - 점선으로 추가사항을 부가설명
      - 순차 다이어그램 (Sequence Diagram)

 ## 확인(verification)과 검증(validation)
  * SW품질의 정의
    정상작동, 완성도 높은 것 , 명시된 요구사항을 만족 시키는 것
  * SW테스팅
    * 블랙박스 테스팅 - 동적테스트, 요구사항 명세서에 기반을 둔 테스팅 기법
    * 화이트 박스 테스팅 - 정적 테스트, 내부구조를 기반으로 테스트케이스를 추출
    * 단위테스트
----
소공 기말범위 start (ch 10 ~ 19) + UnitTest + mock
시작 시간 5:52분 투자할 수 있는 시간 ch당 20분 적어도 4시간 걸림
ch 당 10분씩 줌 -> 1시간 40분에 끝냄 방법(속독, 속타)

 # 분석단계(Elaboration)
  ## UML Class Diagram
  * Objedct - 제목에 밑줄을 그어 표현(스냅샷 느낌)
  * Class - attributes, operations로 구성
  * Attributes - +: public , -: private #:protected
  * Abstract : \<\<abstract>> 라고 표기하거나 {abstract}라고 표기
  * Interface : \<\<interface>> 라고 표기 하거나 동그라미로 표기
  * Dependency(의존) - 점선
    다른 클래스를 그냥 알고있음
  * Association(연관) - 그냥 선
    다른 클래스와 상호작용이 가능 대등한 관계
    * Qualified Association : multiple 한 ele중에서 특정한것을 지칭할 수 잇는가?
  * Aggregation(집합) - 하나의 클래스가 다른 클래스의 레퍼런스를 가지고 있음 비어있는 다이아몬드 Arrow
    * 한쪽이 Call의 입장 한쪽은 부품같은 느낌
    * composition과 aggregation의 구분을 잘 안하기도 한다.
    * aggregation은 개념적인것에서 많이 사용
  * Composition(구성) - 하나의 클래스가 다른 클래스를 소유하고있음 차있는 다이아몬드 Arrow
    * 공유되는 관계가 아니기 때문에 한쪽 끝은 최대 1이 되어야 한다.
    * 주로 하드웨어 모델링에서 사용된다.
  * Inheritance(상속) - 비어있는 arrow
    * Generalization과 같다고 한다.
    * association도 상속된다.
    * multiple inheritance를 허용
    * 깔끔하게 작성할 수 있다.
  * abstract Class : Direct instance를 못만든다.
    [자세히 정리된 사이트](http://www.nextree.co.kr/p6753/)
  ### 어떻게 Class Diagram을 만들 것인가.
  * 명사를 Class로 만들어라
  * 형용사는 attribute value로 만들어라
  * 동사는 Operation으로 만들어라

  ## System Sequence Diagram(SSD)
  * 어떻게 만들까?
    1. 도메인 모델을 만듦
    2. how가 아니라 what에 대한 정보를 찾음
  * 왜 만들까?
    1. 외부 이벤트를 정확하게 알기 위해서
    * actor에 의한 외부 이벤트, 타이머 이벤트, faults or exceptions을 포함해야 함

  * Operation Contract
    * Operation
      * System Operation
        * Operations that the system as a black box component offers in its public interface
      * System Interfaces
        * entire set of system operations across all user cases
    * Cross Reference
    * Preconditions
    * Postcondition
      * 도메인 모델 상태가 어떻게 변화가 되는지를 나타냄
      * 과거형으로 작성
      * 동작
        * instance creation and Deletion
        * Attribute modification
        * Associations Formed and Broken
  * 언제 Contract를 사용할 것인가?
   1. SSD로 표현 가능한것들 중 대부분은 UseCase로 커버 가능
   2. UseCase로 커버 불가능 한 것들을 Contract로 분류하여 커버

 ## Requirement to Design
  * 지금까지는 OOA/D에 대한 내용이였다.
  * 요구를 한번에 완벽하게 받아들이는 것은 불가능 하기 때문에 반복을 통하여 받아들인다.
  * requirement의 80퍼센트정도를 알아냈을 때 elaboration을 그만둔다. 그 다음에 설계작업이나 구현작업을 시작한다.

 ### 디자인 모델(Design Model)
  * Layer 모델 - 레이어를 기반한 설계는 굉장히 간단하지만 효과적이다.
    * 하위의 레이어는 상위의 레이어를 부를 수 없음
    * strict layer
      - 바로 아래 하위 레이어만 접근 가능
    * relaxed layer
      - 하위 모든레이어 접근 가능
    * cohesion - 응집도 (높을 수록 좋음)
    * coupling - 결합도 (낮을 수록 좋음) (GOD class가 있으면 안됨)
    UI Layer 부터 점점 내려가면서 general해 진다.(위로 올라갈수로 Specific)
    * Java에서는 Package마다 하나의 레이어가 들어가게 된다.
    객체지향 설계에서 만든 Domain Model에서 추출하여 Design 단계에서 Class를 만들어 준다. Domain Model로 만들어진 Class들이 그대로 유지가 된다. 현실에 없는 DB나 Loding같은 디자인 단계에서만 나오는 것들도 다시 만들어진게 된다. 그런 것들은 디자인 단계에서 Domain Object라고 한다. 그런 것들이 모두 합쳐저서 비지니스 Logic이 완성되는 것이다.
    * Architecture을 그릴 때 physical한 것과 logical한 것을 동시에 쓰지 않는다.

    * 용어
      * tier - physical한 것을 이야기함 (나머지는 다 logical함)
      * layer - 추상화 내역에서 얼마나 더 specific 한지를 구분
      * partition - 같은 레이어에 있더라도 클래스 들을 다시 나눠주는 것

  * 소프트웨어 아키텍처?
    * 소프트웨어 조직에 대한 중요한 결정을 내리는 Set 그것들의 behavior은 무엇인가?등


 ## Object Design
  * Dynamic model - 논리, 코드의 behavior, 함수의body를 디자인하는데 도움
    * UML dynamic view interaction daigram을 만들면서 유용한 디자인이 일어난다.
    * Interaction Diagrams - 메시지를 통해 어떠헥 상호작용하는지 설명
      * Sequence Diagram
        * Notation
          * Lifeline boxes and lifelines
            * interaction에 참가자를 표현
            * 클래스의 인스턴스라고 정확히 말할 수는 없지만 실질적으로는 맞다.
          * Messages
            * return result를 보여줄 수 있는 두가지 방법
               1. message syntax 이용
               2. activiation bar 끝에 message line을 이용해서 return
            * Synchronous message - response message를 받을 때 까지 기다린다.(실선 검은색 화살표)
            * ASynchronous message - 안기다림 (실선 화살표)
            * Response message(점선 화살표)
          * Activation bar
          * Message to "self" or "this"
        * Fragment
          * alt - Switch와 비슷
          * opt - else 없는 opt와 비슷
          * loop - 반복할 때 사용 (guard : 최소 반복 횟수가 끝났을때부터 시작 false면 break)
          * break - 한개의 operand를 가지고
          * seq - 여러가지 순서 가능
          * strict - 순서는 고정
          * par - 서로 같은곳의 순서는 중요 다른곳끼리는 안중요
          * critical - 요사이 다른애 개입 불가       
        * polymorphism의 표현
          * muliple sequence diagrams 사용
        * Active Object
          * 각 인스턴스는 실행되며 실행스레드를 제어
      * Communication diagram
        * 표기법
          * link - 두 객체사이 navigation과 visibility를 표현하는 두 객체사이의 연결 경로
          * 모든 메시지는 같은 라인에서 흘러감
          * Message Numbering Sequence - 메시지 순서를 sequence number로 표현가능
          * Conditional Message - 조건문이 있을때 참일때만 보내짐
        * 인스턴스 생성
          * create라는 메시지 사용

  * Static model - 패키지, 크래스이름, 특징, 함수 시그니쳐를 저으이하는 데 도움
    * UML class diagram
      * 사용처
        * Domain model - 개념적 관점
          * Association Name은 표시하지만 naviation arrows를 피한다.
          (도메인 모델은 소프트웨어적 관점이 아니기 때문)
        * Design Class Diagram(DCD) - 디자인 관점
          * UML specification을 따른다.
        * Dependency
          * 소스가 타겟을 알고있는 경우
          * 표현법
            * Dependendcy line을 그린다.
  * Test-Driven or Test-First Development
    * 코드를 테스트하기 전에 단위 테스트 코드를 작성하고, 개발자는 모든 production 코드에 대한 단위 테스트 코드를 작성한다.
    
  * OOD(Object Oriented Design)
    * 객체지향 설계 원칙 - 책임을 누구한테 줄것인지
      * GRASP(General Responsibililty Assignment Software Patterns)
        * interaction Diagram을 그릴 때 우리는 객체에 할당할 책임을 결정한다.
        * 누가 어떤 객체를 create 할지
        * 원칙
          * Creater*
          * Controller*
          * Pure Fabrication(제작)
          * Information Expert*
          * High Cohesion*
          * Indirection
          * Low Coupling*
          * Ploymorphism
          * Protected Variations
      * GoF Design Patterns
    * 접근
      * responsibility-driven design(RDD)
        * 객체의 디자인에 더해 더 큰 규모의 구성요소를 생각, 책임, 협력의 관점에서 생각
        * 객체가 책임을 가지고있다고 보고 그들이 하는일을 추상화
        * 책임 (Responsibility)
          * Doing
            * 스스로 무언가를 함
            * 다른 개체에 작업을 시작
            * 기타 개체의 확옹을 동기화 및 제어
          * Knowing
            * Encapsulated data
            * related objects
            * 해당개체가 유도하거나 계산할 수 있는 것에 대해 아는
