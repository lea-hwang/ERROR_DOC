### 키워드
`MEDIA_URL`, `STATIC_URL` 

### 문제 상황
- `MEDIA_URL`, `STATIC_URL` 이 두 값이 같아서 생긴 문제.. 인 것 같은데 내가 짠 코드가 아니라서 뭐라고 수정해야하는 건지..ㅜㅜ
  
  ![image](https://user-images.githubusercontent.com/37495515/235708697-81f12e13-3740-484e-a980-df8ffdbab03a.png)


### 해결 방법
- 일단 `MEDIA_URL`이 뭔지부터 다시 확인해보기로 했다.

  [벨로그글 참고](https://velog.io/@duo22088/Django-Media-file-%EB%8B%A4%EB%A3%A8%EA%B8%B0)
  - `MEDIA_URL`은, 각 media 파일에 대한 URL Prefix을 의미하고, `MEDIA_ROOT`는 실제 파일을 저장할 ROOT 경로를 의미한다.
- `STATIC_URL`, `STATIC_ROOT`도 비슷한 의미이나, `static` 파일에 대한 경로를 의미한다. 
  - images, JavaScript, or CSS 같은 파일
  - [참고](https://docs.djangoproject.com/en/4.2/howto/static-files/)
- `settings.py`을 확인했는데, 이전에 AWS S3 사용하면서 URL들을 변경시킨게 보였다(`MEDIA_URL`이랑 `STATIC_URL`이 같게 설정되어 있었음). 그래서 그 부분 주석처리..하고 원래 있던 URL들을 썼더니

  ![image](https://user-images.githubusercontent.com/37495515/235710738-01d07292-fb72-4047-ae34-436ddcbaf83b.png)
- 해결
  ![image](https://user-images.githubusercontent.com/37495515/235710865-a7996510-e769-4621-8f91-a5cc587d4509.png)

### 느낀점 및 참고
- 울지마 바보야...😂
- 오랜만에 Django 보려니 쉽지 않다...🦆
