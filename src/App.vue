<template>
  <div id="app">
    <MyHeader />
    <div id="content" class="main_content"><MyContent /></div>
    <MyFooter />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyContent from './components/MyContent.vue';
import MyFooter from './components/MyFooter.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyContent,
    MyFooter,
  },
  mounted() {
    const matomo = window._paq; // eslint-disable-line no-underscore-dangle
    matomo.push(['trackPageView']);
    matomo.push(['trackVisibleContentImpressions']);
    matomo.push(['enableJSErrorTracking']);
  },
};
</script>

<style>
@font-face {
  font-family: "Be_Vietnam";
  src: url(./assets/fonts/Be_Vietnam/BeVietnam-Light.ttf);
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "Be_Vietnam";
  src: url(./assets/fonts/Be_Vietnam/BeVietnam-ExtraBold.ttf);
  font-weight: bold;
}

#app {
  font-family: Be_Vietnam, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #181818;
}

html {
  position: relative;
  min-height: 100%;
}

main {
  margin-top: 60px;
  margin-bottom: 60px;
}

.main_content {
  padding-bottom: 160px; /* Margin bottom by footer height */
}

.main_content h2 {
  margin-top: 4rem;
  margin-bottom: 2rem;
  font-size: 1.75rem;
}

.main_content h3 {
  font-weight: bold;
  font-size: 1rem;
}

.main_content ul {
  list-style-type: none;
  padding: 0;
}
.main_content li {
  display: inline-block;
  margin: 0 10px;
}
.main_content a {
  color: #198754;
}

.main_content a:hover {
  color: #6f42c1;
}

.main_content a:active {
  color: #ffc107;
}

.main_content p {
  text-align: justify;
}

/* https://bootsnipp.com/snippets/3Al5m */
.main_content blockquote {
    position: relative;
    text-align: left;
    padding: 1.2em 0 2em 38px;
    border: none;
    margin: 20px auto 20px;
    max-width: 83%;
    width:100%;
    display: block;
}

.main_content blockquote:after {
    content: "";
    display: block;
    width: 2px;
    height: 100%;
    position: absolute;
    left: 0;
    color: #63a62e;
    top: 0;
    background: linear-gradient(to bottom,#181818 0%,#181818 60%,rgba(255,255,255,0) 100%);
}

.main_content blockquote:before {
    /* https://codepen.io/sosuke/pen/Pjoqqp */
    /* filter: invert(49%) sepia(10%) saturate(4339%) hue-rotate(232deg); */
    content: ' ';
    background-image: url("../public/static/quote-left-solid.svg");
    background-repeat: no-repeat;
    opacity: 0.5;
    height: 20px;
    display: block;
    margin-bottom: 0.8em;
}

.main_content blockquote > cite,
.main_content blockquote > p > cite {
    display: block;
    font-size: 16px;
    line-height: 1.3em;
    font-style: normal;
    font-weight: 700;
    margin-top: 1.1em;
    letter-spacing: 0;
    font-style:italic;
}

.main_content blockquote cite::before {
  content: '\2014';
}

.main_content ul {
  list-style-type: square;
  text-align: left;
  max-width: 83%;
  margin: 0 auto;
  margin-bottom: 1rem;
}

.main_content ul li::before {
  content: "\25A0";  /* Add content: \2022 is the CSS Code/unicode for a bullet */
  color: #181818; /* Change the color */
  font-weight: bold; /* If you want it to be bold */
  display: inline-block; /* Needed to add space between the bullet and the text */
  width: 1em; /* Also needed for space (tweak if needed) */
  margin-left: -1em; /* Also needed for space (tweak if needed) */
}

.main_content .btn-purple {
  background-color: white;
  color: #6c757d;
  border-color: #6c757d
}

.main_content .btn-purple:hover {
  background-color: #6f42c1;
  color: white;
}

.main_content .btn-purple:active {
  background-color: #198754;
  color: white;
}

</style>
