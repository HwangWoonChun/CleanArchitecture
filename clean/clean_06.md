# 설계원칙

# Solid 법칙
  * 좋은 벽돌로 좋은 아키텍쳐를 정의하는 원칙
  * 변경에 유연
  * 이해하기 쉽다
  * 많은 소프트웨어 시스템에 사용될 수 있는 컴포넌트의 기반

# Solid 5 가지
  * SRP : single responsbility principle
    * 단일 책임원칙 
      * 각 소프트웨어 모듈은 변경의 이유는 단 하나여야 한다.

  * OCP : open-closed principle
    * 개방-폐쇄 원칙
      * 기존 코드를 수정하기보단 새로운 코드를 추가하는 방식
  
  * LSP : liskov substitution principle
    * 리스코프 치환 원칙
      * 상호 대체 가능한 구성요소를 이용해 소프트웨어 시스템을 만들려면 이들 구송요소는 서로 치환 가능해야 한다.

  * ISP : interface segregation principle
    * 인터페이스 분리 원칙
      * 이 원칙에 따르면 소프트웨어 설계자는 사용하지 않는 것에 의존하지 않는다. 

  * DIP : dependency inversion principle
    * 의존성 역전 원칙
      * 고수준 정책을 구현하는 코드는 저수준 세부사항을 구현하는 코드에 절대로 의존해서는 안된다. 
      * 저수준 세부사항이 정책에 의존해야 한다.
