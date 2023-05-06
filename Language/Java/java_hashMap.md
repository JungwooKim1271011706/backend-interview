

## Q. HashMap의 시간복잡도를 말해주세요.

- HashMap은 (연산에 대해) 상수 시간의 시간복잡도를 갖습니다.



## HashMap은 어떻게 구현되어있길래 그렇게 빠르게 값을 탐색하나요?

- HashMap은 내부적으로 해시 테이블을 갖습니다. 해시맵에 요소가 삽입되면, 해시함수로 이 요소의 key값이 저장될 인덱스 값을 구해서 해시테이블의 해당 인덱스 위치에 요소를 저장합니다. 그래서 이처럼 배열 인덱스를 이용하기 때문에 HashMap에서 값을 탐색할때 상수 시간의 시간복잡도를 갖게 되는 것입니다.

![JavaScript Hash Table – Associative Array Hashing in JS](https://www.freecodecamp.org/news/content/images/2021/05/g983.jpg)