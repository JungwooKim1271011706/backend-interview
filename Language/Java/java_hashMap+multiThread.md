
  

## Q. HashMap과 HashTable의 차이는 무엇인가요?

- HashMap은 동기화를 지원하지 않고, HashTable은 동기화를 지원한다는 차이가 있습니다. 그러므로 HashTable이 동기화를 처리하는 비용 때문에 HashMap에 비해 상대적으로 처리 속도가 느립니다. 또한 HashTable은 key와 value에 null을 허용하지 않고, HashMap은 null을 허용합니다. 