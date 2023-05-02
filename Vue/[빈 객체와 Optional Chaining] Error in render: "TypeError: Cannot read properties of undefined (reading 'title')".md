### 키워드
`?.`, `optional chaining`, `` 

### 문제 상황
- `shot.movie.title`를 불러와야 하는데, shot이 빈 객체여서 불러오지 못하는 상황
   ![image](https://user-images.githubusercontent.com/37495515/235759225-c76dd907-e4c9-4a2e-90dc-c26a69b206ff.png)

    ![image](https://user-images.githubusercontent.com/37495515/235734221-5af0dc1f-3051-43b3-b7d0-97b4e0a4f37c.png)
  
  
### 원인 분석
- 자바스크립트의 특징 중 하나로, undefined에 **존재하지 않는** 속성에 접근하면 다음과 같은 에러가 발생한다.
    
![image](https://user-images.githubusercontent.com/37495515/235762151-93dd8ada-7260-4fa9-91e9-64f5d72f61d7.png)
- 그렇기 때문에 optional chainging(`?.`)을 사용하면 `a.k`의 값이 `undefined`일 때, 그 값도 undefined가 되기 때문에 
- 이러한 방법으로 해결해보려했다.  
    

### 해결 방법
-  `?.` optional chaining 을 이용해서 고쳐보려 했는데 안되더라... 너 왜 안되니?
  
  ![image](https://user-images.githubusercontent.com/37495515/235762706-1ff3b82b-dfff-493b-8103-1ae3f6a50843.png)
  - 아예 `SyntaxError`가 떠버리는 재미있는 상황 ㅎㅎ
  - 알고보니 **template 내부에는 ES2015 이후의 새로운 Syntax를 사용할 수 없다**고 한다..ㅎㅎ [참고](https://junglast.com/blog/vue-template-new-es-syntax)
  - 그래서 이를 개선한 [vue-template-babel-compilier](https://github.com/JuniorTour/vue-template-babel-compiler) 라이브러리가 존재한다고 하는데...!!
  - 사용방법은 매우 간단했다.
    1. 먼저 다음과 같이 모듈을 설치한다.
      ```
        npm install vue-template-babel-compiler --save-dev
      ```
    2. `vue.config.js` 파일을 다음과 같이 수정한다.
      ```
        module.exports = {
          chainWebpack: (config) => {
            config.module
              .rule("vue")
              .use("vue-loader")
              .tap((options) => {
                options.compiler = require("vue-template-babel-compiler");
                return options;
              });
          },
        };
      ```
    3. 해 to the 결

### 느낀점 및 참고
- [MDN - optional chaining](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
- vue는 신기하고도 어려운 느낌이랄까.. 분명 쉽댔는데 에러는 쉽지가 않은 걸요..
