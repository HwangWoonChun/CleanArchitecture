# OCP : 개방-폐쇄원칙
  
  * 개체는 확장에는 열려있어야하고, 변경에는 닫혀있어야 한다.(= 요구사항을 확장하는데 엄청난 수정이 들어가면 안된다.)
  * 아래와 같이 하면 변경량을 최소 화 할 수 있다.
      * 서로 다른 목적으로 변경되는 요소를 적절하게 분리
      * 의존성을 체계화(나누어진 책임이 서로 영향을 끼치지 않도록 한다.)
      
# 사고 실험
  <img src="https://github.com/HwangWoonChun/CleanArchitecture/blob/main/clean/image/07/1.png" width = 300 height = 200>
    * 처리과정을 클래스 단위로 분리 하고 클래스는 컴포넌트 단위로 분리한다. 
    * <I> : 인터페이스, <DS> : 데이터 구조
    * 검정 화살표 : 사용 관계
    * 흰색 화살표 : 구현관계 또는 상속 관계
    * 모든 의존성이 소스코드 의존성을 나타낸다.
      * 화살표가 A 클래스에서 B 클래스로 향한다면, A 클래스에서 B 클래스를 호출 한다는 의미

  <img src="https://github.com/HwangWoonChun/CleanArchitecture/blob/main/clean/image/07/2.png" width = 300 height = 300>
