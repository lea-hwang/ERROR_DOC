### 키워드
`SECRET_KEY`, `decouple`, `SQLite`

### 문제 상황
- `python manage.py migrate`을 해서 DB 만들어주려 하는데, SECRET_KEY가 없대요..

  ![image](https://user-images.githubusercontent.com/37495515/235699926-31681aac-8381-4603-b446-0466fe25560c.png)


### 해결 방법
- `config/settings.py` 확인해보니

  ![image](https://user-images.githubusercontent.com/37495515/235700360-60314d4e-9c1a-49c1-86e7-884301178519.png)
  ```
    from decouple import config
    SECRET_KEY = config('SECRET_KEY')
  ```
  이라고 작성되어 있는 것을 확인. 아마 SECRET KEY 따로 빼주려고 해당 코드를 작성한거 같은데 `decouple`이 뭔지 모르니 검색
  - [decouple](https://hangjastar.tistory.com/198) 사용 방법을 참고하였음.
    ![image](https://user-images.githubusercontent.com/37495515/235701342-d7eb34be-adae-45e6-8da2-2b09e04265dd.png)
  - 그래서 `BASE_DIR`의 위치에 `.env` 파일을 만들고 안에 `SECRET_KEY`를 넣어주었다.(로컬에서 그냥 쓸꺼니까 막 넣었음..)
    ![image](https://user-images.githubusercontent.com/37495515/235701627-c392b006-6c80-4446-839e-fd6442ca8eb1.png)
  - 해결
    ![image](https://user-images.githubusercontent.com/37495515/235702421-85be3b9a-05ff-4958-b15b-be2d65d7b1ed.png)

### 느낀점 및 참고
- 구글링 최공..
- [django sqlite3 사용](https://e-you.tistory.com/354?category=1028321)
- SQLite를 VSC 에서 보기 위해서 extension을 깔아주자!.
  ![image](https://user-images.githubusercontent.com/37495515/235703620-d440d2a7-a49d-401c-aef6-5ef757d434b1.png)
  - Open Database를 누르면
  ![image](https://user-images.githubusercontent.com/37495515/235704125-99ffa64c-a0f1-4925-876a-836cc3757839.png)
  - SQLITE EXPLORER이 생긴다.
  ![image](https://user-images.githubusercontent.com/37495515/235704338-a5718a45-73b2-4e15-87be-eea39e81b1e2.png)


