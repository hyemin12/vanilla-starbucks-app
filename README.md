# Starbucks

[<img src="https://github.com/hyemin12/react-dashboard-app2/blob/master/public/img/portfolio/starbucks.png?raw=true" alt="스타벅스" target="_blank" />](https://wizardly-jennings-ee135b.netlify.app)

이미지를 클릭하면 사이트로 이동합니다.

<br>

### Favicon (파비콘)

<hr>

웹페이지를 나타내는 아이콘, 웹페이지의 로고를 설정<Br>
대부분의 경우 루트 경로에 favicon.ico 파일을 위치하면 자동으로 로딩하기때문에 link하지 않아도 됨<br>
** 파비콘 이미지는 루트 경로에 있어야함
** favicon.ico : 64 x 64 , 32 x 32 , 16 x 16 (px) <br>
\*\* 이미지를 업로드하면 손쉽게 .ico 파일을 제작할 수 있는 홈페이지 ::
https://iconifier.net/

```html
<link rel="shortcut icon" href="favicon.ico" />
<link rel="icon" href="./favicon.png" />
```

### RESET.css

<hr>

브라우저의 기본 스타일을 초기화하는 cdn

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css"
/>
```

### Google Font

<hr>

구글 폰트 사이트<br>
https://fonts.google.com/<br>
모든 사이트에서 동일한 폰트가 출력되도록 설정

```html
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
  href="https://fonts.googleapis.com/css2?family=Nanum+Gothic:wght@400;700&display=swap"
  rel="stylesheet"
/>
```

cdn을 가져와 html head 부분에 붙여넣고, css에 폰트를 적용시킴

```css
body {
  font-family: "Nanum Gothic", sans-serif;
}
```

### Google Material Icons

<hr>

구글에서 제공하는 무료 Icon
https://fonts.google.com/icons?selected=Material+Icons

```html
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
/>
```

cdn을 가져와 html head 부분에 붙여넣고, 태그 클래스에 material-icons 작성 후 사용

```html
<div class="material-icons">upload</div>
```

### 오픈그래프

<hr>

웹페이지가 소셜미디어로 공유될 때 우선적으로 활용되는 정보를 지정<br>
오픈그래프 속성보기 : https://ogp.me/

<img src="https://raw.githubusercontent.com/ParkYoungWoong/starbucks-vanilla-app/master/_assets/kakao_og_example.jpg" width="300px" />

<br>

오픈그래프

```html
<meta property="og:type" content="페이지유형" />
<meta property="og:site_name" content="사이트이름" />
<meta property="og:title" content="페이지 이름" />
<meta property="og:description" content="페이지에 대한 설명" />
<meta property="og:image" content="대표이미지주소(url)" />
<meta property="og:url" content="페이지 링크(url)" />
```

<br>

트위터 카드

```html
<meta property="twitter:card" content="카드 유형" />
<meta property="twitter:site" content="사이트이름" />
<meta property="twitter:title" content="페이지 이름" />
<meta property="twitter:description" content="페이지에 대한 설명" />
<meta property="twitter:image" content="대표이미지주소(url)" />
<meta property="twitter:url" content="페이지 링크(url)" />
```

## 사용한 라이브러리

<hr>

<br>

### 1. GSAP & ScrollToPlugin

<hr>

GSAP : 자바스크립트로 제어하는 타임라인 기반의 애니메이션 라이브러리 <br>
https://greensock.com/gsap/
<br>
ScrollToplugin : 스크롤 애니메이션을 지원하는 GSAP 플러그인
https://greensock.com/scrolltoplugin/

<br>
cdn

```html
<script
  src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/gsap.min.js"
  integrity="sha512-IQLehpLoVS4fNzl7IfH8Iowfm5+RiMGtHykgZJl9AWMgqx0AmJ6cRWcB+GaGVtIsnC4voMfm8f2vwtY+6oPjpQ=="
  crossorigin="anonymous"
></script>
<script
  src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/ScrollToPlugin.min.js"
  integrity="sha512-nTHzMQK7lwWt8nL4KF6DhwLHluv6dVq/hNnj2PBN0xMl2KaMm1PM02csx57mmToPAodHmPsipoERRNn4pG7f+Q=="
  crossorigin="anonymous"
></script>
```

.to() 사용방법

```js
gsap.to(요소, 시간, 옵션);
// 또는
TweenMax.to(요소, 시간, 옵션);
```

- Eg. 페이지 최상단으로 이동

```js
gsap.to(window, 0.7, {
  scrollTo: 0,
});
```

## 2.Swiper

<hr>

슬라이드 라이브러리<br>
https://swiperjs.com/get-started

<Br>

사용방법

```html
<!-- in HEAD -->
<link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css" />
<script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
```

```html
<!-- in BODY -->
<div class="swiper-container">
  <div class="swiper-wrapper">
    <div class="swiper-slide">1</div>
    <div class="swiper-slide">2</div>
    <div class="swiper-slide">3</div>
  </div>
</div>
```

```js
// <-- in Javascirpt -->
new Swiper(".swiper-container", {
  direction: "vertical", // 수직 슬라이드
  autoplay: true, // 자동 재생 여부
  loop: true, // 반복 재생 여부
});
```

### 3.Youtube Api

<hr>

iframe player api를 통해 youtube 동영상 제어
https://developers.google.com/youtube/iframe_api_reference?hl=ko
<br>
<br>
사용방법

```html
<!-- in HEAD -->
<script defer src="./js/youtube.js"></script>

<!-- in BODY -->
<div id="player"></div>
```

```js
// Youtube IFrame API를 비동기로 로드합니다.
var tag = document.createElement("script");
tag.src = "https://www.youtube.com/iframe_api";
var firstScriptTag = document.getElementsByTagName("script")[0];
firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

function onYouTubePlayerAPIReady() {
  // <div id="player"></div>
  new YT.Player("player", {
    videoId: "An6LvWQuj_8", // 재생할 유튜브 영상 ID
    playerVars: {
      autoplay: true, // 자동 재생 유무
      loop: true, // 반복 재생 유무
      playlist: "An6LvWQuj_8", // 반복 재생할 유튜브 영상 ID 목록
    },
    events: {
      // 영상이 준비되었을 때,
      onReady: function (event) {
        event.target.mute(); // 음소거!
      },
    },
  });
}
```

- onYouTubePlayerAPIReady 함수 이름 변경 불가, 전역 등록해야함
- 플레이어 매개변수 : https://developers.google.com/youtube/player_parameters.html?playerVersion=HTML5&hl=ko#Parameters

<br>

### 4.Scroll Magic

<hr>

스크롤과 요소의 상호작용을 위한 자바스크립트 라이브러리
현재화면에 보이는 상태인지를 확인할 때 사용<br>
https://github.com/janpaepke/ScrollMagic
<br>
Scroll Magic Api :
http://scrollmagic.io/docs/
<br>
사용방법

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/ScrollMagic.min.js"></script>
```

```js
new ScrollMagic.Scene({
  // 감시할 장면(Scene)을 추가
  triggerElement: spyEl, // 보여짐 여부를 감시할 요소를 지정
  triggerHook: 0.8, // 화면의 80% 지점에서 보여짐 여부 감시
})
  .setClassToggle(spyEl, "show") // 요소가 화면에 보이면 show 클래스 추가
  .addTo(new ScrollMagic.Controller()); // 컨트롤러에 장면을 할당(필수!)
```

화면의 80%에 도착해서 해당 요소가 화면에 보이면, 클래스 추가!
