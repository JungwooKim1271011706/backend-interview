# [Python] 클래스 변수, 인스턴스 변수

## 인스턴스 변수, Instance variables

**각각의 인스턴스 마다 독립된 변수**

인스턴스 변수를 정리하기 전에 먼저 인스턴스에 대해 설명하고자 합니다.
인스턴스는 클래스로 만들어진 Object 입니다.

아래 그림을 보면 캔디라는 자판기, 카테고리가 있고 여기서 각각의 사탕들이 나옵니다.

![Figure 1. Class candy, Instance candies](./Untitled.png)

Figure 1. Class candy, Instance candies

여기서 각각의 사탕들이 사탕 자판기의 인스턴스이며 
각 사탕이 가지는 값(e.g 제조일자, 색상)이 인스턴스 변수입니다.

## 클래스 변수, Class variables

**모든 인스턴스 사이에 공유된 값을 가지는 변수**

인스턴스 변수와 다르게 공통적으로 가지는 속성이며 인스턴스를 생성하지 않고도 참조하는 것이 가능합니다.

## Example

```python
import os

class GetData():
    # Class variables
    test_list = ['jungwoo', 'esji']

    def __init__(self):
        # Instance variables
        self.file_list = []
        self.except_list = ['.DS_Store', 'README.md']
        
        for filename in os.listdir('data'):
            if filename not in self.except_list:
                self.file_list.append(filename)
```

```python
import GetData as gd

getData = gd.GetData()

# Instance varialbes 
print(f"Instance variables: {getData.file_list}")

# Class variables 정상적으로 확인
print(f"Class variables: {gd.GetData.test_list}")

# Instance variables 테스트
# No attribute Error return
print(f"{gd.GetData.file_list}")
```

```python
~/Workspaces/hy-research develop* research ❯ python util/test.py
Instance variables: ['220117.2144.csv', '220117.2204.csv']
Class variables: ['jungwoo', 'esji']

# ------ Instance variables error -------- #
Traceback (most recent call last):
  File "util/test.py", line 5, in <module>
    print(f"{gd.GetData.file_list}")
AttributeError: type object 'GetData' has no attribute 'file_list'
```