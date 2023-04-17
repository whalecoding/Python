# To-do 리스트
### 프로그램 설명
To-do 리스트 어플리케이션은 내가 해야할 일들을 저장하고 관리하는 프로그램입니다.       
![스크린샷 2022-02-09 오전 10 44 51](https://user-images.githubusercontent.com/48852104/153106045-be4d5f19-882a-4172-bf96-ad00747a214f.png)

해야할 작업을 추가하고, 삭제하고, 목록을 조회하는 프로그램을 만들어보겠습니다.     

<img width="349" alt="image" src="https://user-images.githubusercontent.com/89170523/232436818-4e2f9e8c-ad88-43b3-b312-9734c05e1a05.png">

### 시나리오
프로그램의 기능을 생각하며 메뉴를 구생해보겠습니다.        
프로그램이 제공할 기능은 아래와 같습니다.     
1. 할 일 추가
2. 할 일 지우기
3. 할 일 목록 출력
4. 프로그램 종료

위 메뉴를 사용자가 선택할 수 있도록 출력하고, 입력받는 값에 따라서 알맞은 코드를 실행해보겠습니다.       

큰 흐름은 아래처럼 되겠네요.
1. 메뉴를 출력한다.
2. 사용자의 입력에 따라서 알맞은 코드를 실행한다.
3. 사용자의 입력이 4가 될때까지 2번을 반복한다.

대략 작성할 코드 시나리오를 그려보겠습니다.
```python
반복 시작
  선택 메뉴를 출력한다.
  사용자로부터 숫자를 입력받는다.
  만약 입력받은 숫자가 1이라면
      할일 항목을 입력받는다.
      todo 리스트에 추가한다.
  입력받은 숫자가 2라면
      할일 항목을 입력받는다.
      todo 리스트에서 제거한다.
  입력받은 숫자가 3이라면
      todo 리스트를 보기 좋게 출력한다.
  입력받은 숫자가 4라면
      프로그램을 종료한다.
반복 끝
```
흐름이 보이나요?       
이대로 코딩해보겠습니다.

### 
사용자의 선택을 도와줄 수 있도록 '메뉴출력'이라는 함수를 하나 만들어 주겠습니다.
```python
def 메뉴출력():
    print("To-do 리스트")
    print("1. 할 일 추가하기")
    print("2. 할 일 지우기")
    print("3. 할 일 목록")
    print("4. 프로그램 종료하기")
```
메뉴를 출력할때 위 함수를 사용하겠습니다.     

그리고 todo 목록을 관리할 리스트 변수도 하나 생성하겠습니다.
```python
def 메뉴출력():
    print("To-do 리스트")
    print("1. 할 일 추가하기")
    print("2. 할 일 지우기")
    print("3. 할 일 목록")
    print("4. 프로그램 종료하기")

# 할일 목록이 저장될 리스트
todos = []
```
이제 프로그램 흐름에 따라서 코딩을 해봅시다.      
반복이 코드의 처음부터 끝까지 되고 있습니다.      
`while True` 가 처음부터 등장하겠네요.     
그리고 그 안에 메뉴를 출력하고 사용자의 입력을 계속해서 받는 코드를 추가하겠습니다.

```python
def 메뉴출력():
    print("To-do 리스트")
    print("1. 할 일 추가하기")
    print("2. 할 일 지우기")
    print("3. 할 일 목록")
    print("4. 프로그램 종료하기")

todos = []

# 반복시작
while True:
    # 메뉴 출력 함수 호출
    메뉴출력()
    # 메뉴 선택
    command = input("원하는 작업을 선택하세요 --> ")
    
# 반복 종료
```
선택한 메뉴에 따라서 분기되는 코드를 만들어봅시다.       
```python
def 메뉴출력():
    print("To-do 리스트")
    print("1. 할 일 추가하기")
    print("2. 할 일 지우기")
    print("3. 할 일 목록")
    print("4. 프로그램 종료하기")

todos = []

# 반복시작
while True:
    메뉴출력()
    command = input("원하는 작업을 선택하세요 --> ")
    if command == '1':
        # todo리스트 추가
    elif command == '2':
        # todo리스트 삭제
    elif command == '3':
        # todo리스트 출력
    elif command == '4':
        # 프로그램 종료
# 반복 종료
```

여기에 원하는 코드들을 채워넣으면 되겠네요.
선택한 메뉴에 따라서 분기되는 코드를 만들어봅시다.     

```python
def 메뉴출력():
    print("To-do 리스트")
    print("1. 할 일 추가하기")
    print("2. 할 일 지우기")
    print("3. 할 일 목록")
    print("4. 프로그램 종료하기")

todos = []

# 반복시작
while True:
    메뉴출력()
    command = input("원하는 작업을 선택하세요 --> ")
    if command == '1':
        # todo리스트 추가
        print(">>> 할 일 추가하기")
        todo = input("항목을 입력하세요: ")
        todos.append(todo)
    elif command == '2':
        # todo리스트 삭제
        print(">>> 할 일 지우기")
        todo = input("항목을 입력하세요: ")
        todos.remove(todo)
    elif command == '3':
        # todo리스트 출력
        for todo in todos:
            print(todo)
    elif command == '4':
        # 프로그램 종료
        print(">>> 프로그램을 종료합니다.")
        break
# 반복 종료
```
프로그램이 완성되었습니다!

### 마무리
문자열 리스트(todo)에 할일들을 저장해 놓았습니다.    
그리고 todo 리스트를 for문을 사용하여 출력하고     
사용자의 입력을 받아서 리스트를 추가, 삭제하였습니다.       
프로그램을 종료하도록 if문과 break 를 사용합니다.       

프로그램이 어떻게 되면 더 유용하게 사용이 될까요?    
추가할 기능을 생각하며 자유롭게 프로그램을 발전시켜 봅시다.

### 결과
```python
def 메뉴출력():
    print("To-do 리스트")
    print("1. 할 일 추가하기")
    print("2. 할 일 지우기")
    print("3. 할 일 목록")
    print("4. 프로그램 종료하기")

todos = []

# 반복시작
while True:
    메뉴출력()
    command = input("원하는 작업을 선택하세요 --> ")
    if command == '1':
        print(">>> 할 일 추가하기")
        todo = input("항목을 입력하세요: ")
        todos.append(todo)
    elif command == '2':
        print(">>> 할 일 지우기")
        todo = input("항목을 입력하세요: ")
        todos.remove(todo)
    elif command == '3':
        for todo in todos:
            print(todo)
    elif command == '4':
        print(">>> 프로그램을 종료합니다.")
        break
```


