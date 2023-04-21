

# [JAVA] static 키워드



## static 이란?

- static 메서드와 static 필드는 객체(인스턴스)에 소속된 게 아니라 클래스에 고정된 멤버이기 때문에 클래스 로더(class loader)가 클래스를 로딩할 때 생성되며 JVM이 종료될 때까지 유지된다.

- heap이 아닌 static 영역(Method Area)에 할당된다. 그러므로 GC(Garbage Collector)가 관여하지 않는다.

  ![JVM Memory area parts](https://media.geeksforgeeks.org/wp-content/uploads/Memory.png)

  



## static 사용 이유

1. **메모리 사용을 최적화할 수 있다.**

   - 인스턴스 변수는 객체 생성시마다 메모리를 사용하지만 (heap에 저장됨), static 변수는 한번만 할당된다.

2. **인스턴스 생성과 관련 없이 공통된 값이 필요할 때마다 사용할 수 있다.**

   - ex) `Math` 클래스의 `PI`상수.

   

   ## static 사용시 주의사항

   - static 변수의 값을 변경하면 모든 인스턴스에서 해당 값이 변경되므로 static 변수를 공유하는 모든 객체에 영향을 미칠 수 있다.

   - 멀티스레드 환경에서는 여러 스레드가 동시에 static 변수에 접근하는 경우가 발생할 수 있다. 이때 스레드 간에 실행순서나 타이밍에 따라 변수에 접근하는 순서가 달라져 (race condition) 결과가 예상대로 나오지 않을 수 있다. 이를 방지하기 위해선 적절한 동기화 기법을 사용해서 여러 스레드가 static 변수에 동시에 접근하는 것을 막야아 한다. (스레드 안정성 보장)

     

   아래는 예시 코드이다.

```java
// 동기화 기법 미적용
public class SharedStaticVariableExample {
    public static int sharedVariable = 0;

    public static void main(String[] args) {
        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 10000; i++) {
                sharedVariable++;
            }
        });

        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 10000; i++) {
                sharedVariable++;
            }
        });

        thread1.start();
        thread2.start();

        try {
            thread1.join();
            thread2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        // 결과가 예상대로 나오지 않을 수 있다
        System.out.println("Shared variable value: " + sharedVariable);
    }
}

// 동기화 적용 : synchronized 키워드 사용 
public class SharedStaticVariableExample {
    public static int sharedVariable = 0;

    public static synchronized void incrementSharedVariable() {
        sharedVariable++;
    }

    public static void main(String[] args) {
        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 10000; i++) {
                incrementSharedVariable();
            }
        });

        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 10000; i++) {
                incrementSharedVariable();
            }
        });

        thread1.start();
        thread2.start();

        try {
            thread1.join();
            thread2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Shared variable value: " + sharedVariable);
    }
}

```



----

# 참고자료

- https://www.geeksforgeeks.org/java-memory-management/

