# LSP : 리스코프 치환 원칙
  
  * 타입을 치환 하더라도 행위는 바뀌지 않는다.


# 상속을 사용하도록 가이드하기
  <img src="https://uchanlee.dev/static/2602e08dd5e4b86d136e5860b7726449/1bba8/image-9.1.png">
  
    * 빌링 어플리케이션 행위가 라이센스 하위 타입 중 무엇을 사용하는지에 전혀 의존하지 않는다. 고로 LSP 를 준수한다.
    * 하위타입은 모두 라이센스타입을 치환 할 수 있다.
    
# 정사각형/직사각형 문제 square/rectangle - LSP 위반 문제

  <img src="https://uchanlee.dev/static/0bb1fe33b3e2479c58cba7ae2433dd0e/42a8d/image-9.2.png">
    
    * 문제
      * Rectangle 의 높이와 너비는 서로 독립적으로 변경 가능
      * Square의 높이와 너비는 반드시 함께 변경
      
    * User 와 대화하는 상대는 Rectangle 이기때문에 혼동 발생
    * User 의 행위가 사용하는 타입에 의존하게 되므로 결국 타입을 서로 치환 할 수 없다.
    
# LSP와 아키택쳐

  * 아키텍쳐 관점에서 LSP 를 이해하는 최선의 방법은 이 원칙을 어겼을 때 시스템 아키텍쳐에서 무슨 일이 일어나는지 관찰 하는 것이다.
