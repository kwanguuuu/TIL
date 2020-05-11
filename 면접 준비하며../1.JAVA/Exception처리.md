### Java Exception의 종류



### 에러(Error)와 예외(Exception)

에러 : JVM실행의 문제가 생긴 것으로.

- 하드웨어 오작동 또는 고장으로 응용프로그램 실행 오류

예외 : 사용자의 잘못된 조작 또는 개발자의 잘못된 코딩으로 발생한 프로그램 오류

- 예외 처리를 통해 프로그램을 종료하지 않고 정상 실행 상태가 되도록 유지해야함



### 예외의 종류

일반 예외, 실행 예외

일반예외는 **컴파일 체크** 예외라고도 함. -> 자바 소스를 컴파일 하는 과정에서 예외 처리가 필요한지 검사하기 떄문이다.

실행예외는 컴파일 과정에서 예외처리 코드를 검사하지 않는 예외라고 함.

모든 예외 클래스는 java.lang.Exception을 상속 받는다.

일반예외의 부모는 Exception 클래스이고, 실행예외(런타임예외)는 Exception을 상속받은 RuntimeException 클래스를 상속 받는 클래스들이다.

JVM은 RuntimeException의 상속 유무를 보고 실행예외인지를 판단한다.



### 실행예외

JVM이 체크를 하지 않기 때문에 개발자가 직접 예외처리를 해야만 한다.

해당 예외가 발생하면 프로그램이 종료된다.



### 일반적으로 만나는 실행예외들

- NullPointerException
- ArrayIndexOutOfBoundsException
- NumberFormatException
- ArithmeticException