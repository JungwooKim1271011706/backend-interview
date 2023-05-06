

## Q. HashMap과 HashTable의 차이는 무엇인가요?

- HashMap은 동기화를 지원하지 않고, HashTable은 동기화를 지원한다는 차이가 있습니다. 그러므로 HashTable이 동기화를 처리하는 비용 때문에 HashMap에 비해 상대적으로 처리 속도가 느립니다. 또한 HashTable은 key와 value에 null을 허용하지 않고, HashMap은 null을 허용합니다. 



## Q. HashMap은 멀티 스레드 환경에서 안전하지 않은데 thread-safe하게 사용하려면 어떻게 해야 할까요?

- Concurrent 패키지에서 제공하는 `ConcurrentHashMap`또는 util패키지의 `HashTable`을 사용하면 됩니다. 

  

## Q. HashTable과 ConCurrentHashMap 간의 차이점은 무엇인가요?

- ConcurrentHashMap은 검색 연산시에는 lock을 사용하지 않고, HashTable은 모든 연산에 대해 synchronized 키워드를 사용해서 항상 락이 걸린다는 차이가 있습니다. 그래서 ConcurrentHashMap이 HashTable보다 성능적으로 우수하다고 볼 수 있습니다.

