# SRP : 단일 책임 원칙
  
  * 단일 모듈은 변경의 이유가 하나, 오직 하나뿐이어야 한다.
  * 하나의 모듈은 하나의. 오직 하나의 사용자 또는 이해관계자에 대해서만 책임져야 한다.
  
# 우발적 중복

  * 3가지 메서드가 서로 매우 다른 세명의 액터를 책임 지는 상황
  
    ```swift
    protocol Employee {
        func caclulatePay()
        func reportHours()
        func save()
    }

    class CFO: Employee {}
    class COO: Employee {}
    class CTO: Employee {}
    ``` 
      * caclulatePay 는 회계팀에서 기능을 정의하고 CFO 보고를 위해 사용한다.
      * reportHours 는 인사팀에서 기능을 정의하고 사용하며 COO 보고를 위해 사용한다.
      * save는 DBA가 가능을 정의하고 CTO 보고를 위해 사용한다.

  * 이런 경우 어느 액터를 위해 특정 함수를 수정을 하게 되어 다른 액터에 업무적 수치적으로 피해를 발생시킨다.
  
  * 서로 다른 액터가 의존하는 코드를 서로 분리해야 한다.
