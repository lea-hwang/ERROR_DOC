### keyword
`python`, `downgrade`, `requirements.txt`, 

### 상황 및 해결
- 가상환경을 만든 뒤, `pip install -r requirements.txt`을 실행했는데 다음과 같은 에러를 만남.
![image](https://user-images.githubusercontent.com/37495515/235696767-dc780145-90fc-46cd-9715-b10d1dcf59d5.png)

### 해결 방법
1. 패키지 업그레이드 하면 된다 그래서 모두 업그레이드 함 -> 해결 ❌
  ```
    pip install wheel setuptools pip --upgrade
  ```
2. 다시 찾아보니 파이썬 버전을 다운그레이드 하면 해결할 수 있다해서 다운그레이드 함(3.11.X -> 3.10.X)
  - 정확히 말하면, 다운그레이드 버전의 파이썬을 다운 받고 새로운 가상환경을 다운그레이드된 버전으로 틀었음.
  ```
    $ py -3.10 -m venv .venv
    $ pip install -r requirements.txt
  ```
  - 해결
  ![image](https://user-images.githubusercontent.com/37495515/235698063-00c21116-13d5-46ef-b56d-98490802a8d4.png)

### 느낀점 및 참고
- 😂감격 그잡채😂
- 제발 버전 확인하자 희원아!!!!@!!@!@!@!
