## PWA

PWA는 앱처럼 모바일에 설치가능할 수 있게 하는 것(실제로는 웹인데)



PWA 장점

1. 설치 마케팅 비용 적음

2. 아날로그 유저들 배려
3. html, css, js만으로 앱까지
4. 푸시알림, 센서 등



PWA 만드려면 새로운 프로젝트 만들기

```
npx create-react-app 프로젝트명 --template cra-template-pwa
```



기존에 만든 프로젝트를 PWA로 만드려면 코드 복붙하는 수밖에.. 애초에 처음부터 PWA로 만들어야 한다.





PWA의 조건

1. mainfest.json 이 있어야 하고
2. service-worker.js 가 있어야 한다.

3. 위 두개가 PWA 프로젝트 생성할때 자동으로 만들어지긴 한다.





```
manifest.json

{
  "short_name": "React App",
  "name": "Create React App Sample",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}

```



```
index.js

serviceWorkerRegistration.unregister();

이거를

serviceWorkerRegistration.register();

이렇게 바꿔라
```





그리고



```
npm run build
```



그러면

build 폴더에 

manifest.json 이랑 service-worker.js 파일이 생긴다.

그리고 build 폴더를 새로운 vs코드 창에서 열고  index.html 실행해보면

새로운 웹페이지가 뜬다.

특정 페이지 캐싱 안되게 하려면 강의 참고