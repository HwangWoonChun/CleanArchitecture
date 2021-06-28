# OCP : 개방-폐쇄원칙
  
  * 개체는 확장에는 열려있어야하고, 변경에는 닫혀있어야 한다.(= 요구사항을 확장하는데 엄청난 수정이 들어가면 안된다.)
  * 아래와 같이 하면 변경량을 최소 화 할 수 있다.
      * 서로 다른 목적으로 변경되는 요소를 적절하게 분리
      * 의존성을 체계화(나누어진 책임이 서로 영향을 끼치지 않도록 한다.)
      
# 사고 실험
  <img src="https://github.com/HwangWoonChun/CleanArchitecture/blob/main/clean/image/07/1.png" width = 411 height = 329>
  
    * 처리과정을 클래스 단위로 분리 하고 클래스는 컴포넌트 단위로 분리한다. 
    * <I> : 인터페이스, <DS> : 데이터 구조
    * 검정 화살표 : 사용 관계
    * 흰색 화살표 : 구현관계 또는 상속 관계
    * 모든 의존성이 소스코드 의존성을 나타낸다.
      * 화살표가 A 클래스에서 B 클래스로 향한다면, A 클래스에서 B 클래스를 호출 한다는 의미

  <img src="https://github.com/HwangWoonChun/CleanArchitecture/blob/main/clean/image/07/2.png" width = 388 height = 264>
  
    * 컴포넌트관계는 단방향으로만 이루어진다.
    * A 컴포넌트에서 발생한 변경으로 부터 B 컴포넌트를 보호하려면 A 컴포넌트가 B 컴포넌트에 의존 해야 한다.
      * Presenter 에서 발생한 변경으로 부터 Controller 를 보호하려고 한다. (뷰와 모델 사이 연결 매개체)
      * View 에서 발생한 변경으로 부터 Presenter 를 보호하려고 한다.
      * Interactor 는 다른 모든 것에서 발생한 변경으로 부터 보호 하고자 한다. (비즈니스 로직)
    * 보호 수준 : View < Presenter < Controller or Interactor
    
# 방향성 제어

  * 첫번째 그림은 컴포넌트 간 의존성이 제대로 된 방향으로 향하고 있음을 다시 확인 하자.
  * FinancialDataGateWay 는 FinancialReportGenerator와 FinancialDataMapper 사이에 위치하는데 이는 의존성 역전을 위해서다.
    * 모듈간의 의존성을 낮추기 위해 사용되는 패턴으로 모듈 인스턴스의 구성이 추상화에 의존하는 것을 뜻한다.
  * FinancialDataGateWay 가 없다면 의존성이 Interactor 컴포넌트에서 Database 컴포넌트로 바로 향하게 된다.

# 정보은닉

  * FinancialReportRequest 인터페이스는 방향성 제어와는 다른 목적을 가진다.
  * FinancialReportController 가 Interactor 내부에 대해 많이 알지 않도록 막기 위해서 존재 한다.
  * FinancialReportRequest 가 없다면 Controller 는 FinancialEntities 에 대해 추이 종속성을 가지게 된다.
    * 클래스 A가 B에 의존하고 B가 C에 의존한다면 A는 C 에 의존하게 된다.
