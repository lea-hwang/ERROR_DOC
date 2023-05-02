### 키워드
`ALLOWED_HOSTS` 

### 문제 상황
- `python manage.py runserver`했는데, 다음과 같은 에러 발생.

  ![image](https://user-images.githubusercontent.com/37495515/235715644-19679911-d440-43de-8c98-7b88bcef231a.png)


### 해결 방법
- [ALLOWED_HOSTS](https://wikidocs.net/9828)의 내용을 확인해보니 `settings.py`의 `ALLOWED_HOSTS`에 로컬 호스트 설정을 해줘야 할 것같아서 그렇게 설정해주었다.
  
  ![image](https://user-images.githubusercontent.com/37495515/235716989-cfc9916f-accc-481e-8a37-f1c568885d28.png)

- 해 to the 결
  
  ![image](https://user-images.githubusercontent.com/37495515/235717162-7a6d28f0-0904-489f-ba50-4dac6bab7e66.png)
  
- 그런데,, DEBUG = True이면 ALLOWED_HOSTS에 자동으로 로컬호스트가 들어간다는 글 발견.. [참고](https://blog.joonas.io/58)
- 자세히 알아보기 위해 결국 공식 문서 탐방
  ![image](https://user-images.githubusercontent.com/37495515/235720269-a65e7eb3-6469-4f56-a7ad-76d188d47460.png)
- 알고보니 `DEBUG = True`이고, `ALLOWED_HOSTS = []` 이면 자동으로 들어가는 거였다..
- 그래서 바꿀 필요가 없긴 하지만 그냥 바꿔줬다.
- 해 to the 결 2

  ![image](https://user-images.githubusercontent.com/37495515/235720528-c918dbd7-1a73-41f1-b3b3-d5ec9467aef6.png)


### 느낀점 및 참고
- settings.py.. 너 정말..ㅠ
