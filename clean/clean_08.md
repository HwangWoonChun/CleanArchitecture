# OCP : 개방-폐쇄원칙
  
  * 개체는 확장에는 열려있어야하고, 변경에는 닫혀있어야 한다.(= 요구사항을 확장하는데 엄청난 수정이 들어가면 안된다.)
  * 아래와 같이 하면 변경량을 최소 화 할 수 있다.
      * 서로 다른 목적으로 변경되는 요소를 적절하게 분리
      <img src="https://github.com/HwangWoonChun/CleanArchitecture/blob/main/clean/image/07/1.png" width = 300 height = 300>

      * 의존성을 체계화(나누어진 책임이 서로 영향을 끼치지 않도록 한다.)
      <img src="https://github.com/HwangWoonChun/CleanArchitecture/blob/main/clean/image/07/2.png" width = 300 height = 300>

# 징후 1 : 우발적 중복
