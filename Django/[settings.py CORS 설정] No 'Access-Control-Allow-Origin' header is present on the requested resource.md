### 키워드
`CORS`, `decouple`, `.env`

### 문제 상황
- 크크, 너 왜 안나오나 했다 CORS ㅎ
![image](https://user-images.githubusercontent.com/37495515/235720923-1a8fa223-6487-424e-91ee-228bab24d38e.png)
```
cess to XMLHttpRequest at 'http://localhost:8000/api/v1/movies/search/0/' from origin 'http://localhost:8080' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

### 해결 방법
- `settings.py`에 `CORS_ALLOWED_ORIGINS`에 추가시켜주면 된다!
- 근데 역시나 내가 짠 코드 아닌지라..
  ![image](https://user-images.githubusercontent.com/37495515/235721253-3279f771-4278-4b4e-b660-642317506eda.png)
- 그래서 원래 짜여져 있는 코드를 참고해서 수정해보기로 했다.
- 먼저 [decouple](https://pypi.org/project/python-decouple/) 내용을 확인해본 결과
  
  ![image](https://user-images.githubusercontent.com/37495515/235722228-d5a76939-fa09-4027-a9dd-c4a619b78285.png)
  - 요런 느낌으로 사용한다고 하니, `.env`파일을 고쳐보는 걸루! 삽질 한시간 한 결과.. 해결..하
  ![image](https://user-images.githubusercontent.com/37495515/235730245-62f3c6c4-15b2-4681-8f0d-d60d2c78fef6.png)
    - ❗❗❗❗ `.env` 파일 작성할 때 `=` 앞뒤로 띄어쓰기 금지.. 안먹힌다...ㅎㅎ^^
- 해 to the 결
  ![image](https://user-images.githubusercontent.com/37495515/235730623-9925fe31-3acd-4277-97b1-3b0c43aa2ce6.png)

  
### 느낀점 및 참고
- 오늘도 삽질 완료...
