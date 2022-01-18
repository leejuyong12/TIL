# Vue 프로젝트 만들기

### 1. Vue-cli 생성

vue-cli 사이트 방문

git-bash

- npm install -g @vue/cli 



vue 프로젝트 생성

gitbash

- vue create 프로젝트명

(* preset은 플러그인의 집합)

- manually select features
- Babel, Linter/Formatter, Unit 선택
- ESLint + prettier
- Lint on save
- Jest
- In dedicated config files
- n

(* vue 3는 devtools beta로 받아야한다. - 구글 확장프로그램)



gitbash

- cd 프로젝트명
- npm run serve 



ESLint  에러가 화면에 나타나지 않게 하는 방법(오류날때 웹 페이지에 검은색 화면 나오는 거)

- 프로젝트 내에서 새파일 만들기(vue.config.js)

  ```
  module.exports = {
  	devServer: {
  		overlay: false
  	}
  };
  ```

  



.eslintrc.js 파일

ESLint 는 에러가 날 수 있는 것들을 사전에 제거하는 것(보조검사)

https://prettier.io/docs/en/install.html

```
rules: {
    'prettier/prettier': [ 'error', {
        singleQuote: true,
        semi: true,
        useTabs: true,
        tabWidth: 2,
        trailingComma: 'all',
        printWidth: 80,
        bracketSpacing: true,
        arrowParens: 'avoid',
      },
    ],
```



왼쪽에서 eslint 검색 해서 install 하기(주황색)



설정 - eslint

- Eslint: probe - 자스, 자스리액트, 타입스크립트, 타입스크립트리액트, html, vue

- Eslint:validate - 편집 - eslint.validate (모르겠으면 깃헙 코드 참고)

  - 밑에 코드 넣기

  - ```
    {
      // ESLint
      "eslint.validate": [
        {
          "language": "vue",
          "autoFix": true
        },
        {
          "language": "javascript",
          "autoFix": true
        },
        {
          "language": "javascriptreact",
          "autoFix": true
        },
        {
          "language": "typescript",
          "autoFix": true
        },
        {
          "language": "typescriptreact",
          "autoFix": true
        }
      ],
      "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
      },
      // don't format on save
      "editor.formatOnSave": false
    }
    ```



prettier code for - 설치후 - 사용안함(작업영역) - 설정 가서 - format on save 검색 하고 - editor format on save 체크 해제 - 오른쪽밑에 Formatting: X 확인



### 절대경로로 설정하기

프로젝트 내부에 jsconfig.json 파일 생성

```
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "~/*": [
        "./*"
      ],
      "@/*": [
        "./src/*"
      ],
    }
  },
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```



### vue 스타일 가이드

https://kr.vuejs.org/v2/style-guide/index.html



## 라우터 & 컴포넌트 설계

npm i vue-router



routes 폴더 생성 - index.js



views 폴더 생성 - 그 안에 파일 생성



### 코드스플리팅

SPA를 위해

```
			path: '/login',
			component: () => import('@/views/LoginPage.vue'),
		},
		{
			path: '/signup',
			component: () => import('@/views/SignupPage.vue'),
		},

```



### 콜백 기능

없는 라우터에 대해 반응하는 것

```
		{
			path: '*',
			component: () => import('@/views/NotFoundPage.vue'),
```



### history mode - 배포할때는 유의(공식문서참고)

https://router.vuejs.org/kr/guide/essentials/history-mode.html

url 에 # 이 사라진다

```
	mode: 'history',
```



### 회원가입 API 요청

signupform.vue  에서 submitForm 하기 전에

npm i axios  해주기



API 폴더 생성해서 한번에 해결해버리기



.env.production  - 배포용 - https://~~.com/ 이런 형태

.env.development - 개발용 - localhost

.env - production 과 development 가 혹시나 없을때 대비용