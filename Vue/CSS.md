# CSS

- html 영역에서 style 적용할때 뒤에 ; 적용해야 반영된다.
- 이미지 위에 이미지 하려면 배경은 relative 그 위 이미지는 absolute
- keyframes 활용해보기



특정영역으로 이동하기

```
window.scroll({ top: 2500, left: 0, behavior: 'smooth' });
```

```
window.scroll({ top: 0, left: 0, behavior: 'smooth' });
```

```
document.querySelector('header').scrollIntoView({ behavior: 'smooth' });
```
