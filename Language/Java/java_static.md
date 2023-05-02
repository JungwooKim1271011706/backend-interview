

# [JAVA] static 키워드



## Q. static 키워드에 대해 아는대로 설명해주세요.

- static 키워드가 붙은 메서드와 필드는 인스턴스에 소속되지 않고, 클래스에 고정된 멤버이기 때문에 클래스 로더(class loader)가 클래스를 로딩할 때 생성되며, JVM이 종료될 때까지 유지됩니다. 또한 자바 메모리 영역에서 heap이 아닌 static 영역(Method Area)에 할당되기 때문에 GC(Garbage Collector)가 관여하지 않는다는 특징이 있습니다.

![JVM Memory area parts](https://media.geeksforgeeks.org/wp-content/uploads/Memory.png)



## Q. static 키워드를 사용하는 이유가 뭘까요?

- 인스턴스 멤버는 객체 생성시마다 heap 영역에 저장되어 메모리를 사용하지만, static 멤버는 객체 생성시에 한번만 할당되기 때문에 불필요한 메모리 할당을 막아 메모리 사용을 최적화할 수 있다는 장점이 있습니다. 
- 그러므로 Java에서 `Math`클래스의 `PI`상수처럼 변경되지 않는 상수값을 사용할 경우 또는 모든 인스턴스가 공유하는 변수를 선언할 경우 static키워드를 사용하면 메모리 사용을 최적화할 수 있습니다. 
- 또한 유틸리티 클래스를 만들 때 static키워드를 사용하여 메서드를 만들면 인스턴스 생성 없이 유틸리티 메서드를 사용할 수 있어 유틸리티 메서드를 사용하기 위해 인스턴스를 생성할 필요 없어 불필요한 메모리 할당을 줄일 수 있습니다. 



## Q. static 키워드 사용시 주의사항/단점은 무엇일까요?

- static 변수의 값을 변경하면 모든 인스턴스에서 해당 값이 변경되므로 static 변수를 공유하는 모든 객체에 영향을 미칠 수 있습니다. 그러므로 주로 변경되지 않는 상수에 static키워드를 사용하는 것이 좋습니다. 
- 또한 static 멤버는 프로그램이 종료될 때까지 메모리에 남아있으며 GC가 관리하는 영역이 아니기 때문에 메모리 누수가 발생할 가능성이 있습니다.



----

# 참고자료

- https://www.geeksforgeeks.org/java-memory-management/

- https://stackoverflow.com/questions/2472690/in-java-is-there-any-disadvantage-to-static-methods-on-a-class