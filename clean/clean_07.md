# SRP : 단일 책임 원칙
  
  * 단일 모듈은 변경의 이유가 하나, 오직 하나뿐이어야 한다.
  * 하나의 모듈은 하나의. 오직 하나의 사용자 또는 이해관계자에 대해서만 책임져야 한다.
  
# 징후 1 : 우발적 중복

  * 예시) 3가지 메서드가 서로 매우 다른 세명의 액터를 책임 지는 상황
  
    ```swift
    protocol Employee {
        func caclculatePay()
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

  * 이런 경우 어느 액터를 위해 개발자가 특정 함수를 수정을 하게 되면 다른 액터에 업무적 수치적으로 피해를 발생시킬 수 있다.
  
  * 서로 다른 액터가 의존하는 코드를 서로 분리해야 한다.

# 징후 2 : 병합

  * 예시) 체크아웃 후 서로 다른 개발자 들이 병합하면서 충돌 발생
  
  * 서로 다른 액터를 뒷받침하는 코드를 서로 분리해야 한다.

# 해결책 

  * 데이터와 메서드를 분리 
  
    * 3개의 클래스를 인스턴스화 하고 추적해야 되는 단점 
    
    ```swift
    protocol Employee {
    }

    class CFO: Employee {
        func calculatePay() {

        }
    }
    class COO: Employee {
        func reportHours() {

        }
    }
    class CTO: Employee {
        func save() {
        }
    }
    ```
    
   * 퍼사드 패턴을 이용 : 복잡한 클래스 시스템에서 간단한 인터페이스를 제공하는 구조 설계

      ```swift
      protocol Employee {
      }

      class EmployeeFacade {
          private var cfo: CFO
          private var coo: COO
          private var cto: CTO

          init(cfo: CFO, coo: COO, cto: CTO) {
              self.cfo = cfo
              self.coo = coo
              self.cto = cto
          }
      }

      class CFO: Employee {
          func calculatePay() {

          }
      }
      class COO: Employee {
          func reportHours() {

          }
      }
      class CTO: Employee {
          func save() {
          }
      }
      ```
