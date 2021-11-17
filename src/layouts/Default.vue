<template>
  <div class="layout">

    <slot/>
  </div>
</template>



<style>
@font-face {
	font-family: 'Conv_Ubuntu-LI';
	src: url('../assets/fonts/Ubuntu-LI.eot');
	src: local('☺'), url('../assets/fonts/Ubuntu-LI.woff') format('woff'),
  url('../assets/fonts/Ubuntu-LI.ttf') format('truetype'),
  url('../assets/fonts/Ubuntu-LI.svg') format('svg');
	font-weight: normal;
	font-style: normal;
}
body {
    font-family:  'Conv_Ubuntu-LI', sans-serif;
    font-weight: normal;
    font-style: normal;
    margin: 0;
    padding: 0;
    border: 0;
    background-color: #000;
    display: flex;
    justify-content: center;
}
section {
  display: none;
  min-height: 110vh;
}
.figure {
  overflow: hidden;
  width: 99vw;
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  display: block;
  position: relative;
}
.figure:before {
  box-shadow: inset 1vh 1vw 12vw 7vw rgba(0, 0, 0, 0.9);
  content: "";
  height: 100%;
  position: absolute;
  width: 100%;
}
img {
  width: 100%;
}
img:hover {
transform: scale(1.1,1.1) rotate(1deg);
transition: all 50s;
}
@media screen  and (orientation: portrait) {
  h3 {
    font-size: 1.4rem;
    z-index: 44;
    padding: 10vh 0;
  }
  a, ul, ol, p {
      color: #fff;
      max-width: 90vw;
      font-size: 1.2em;
      padding: 10vh 0;
      line-height: 1.1em;
  }
}
@media screen  and (orientation: landscape) {
  h3 {
    font-size: 2.4rem;
    position: relative;
    top: 30vh;
    z-index: 44;
    padding-left: 10vw;
    margin-top: -20vh;
  }
  a, ul, ol, p {
      color: #fff;
      max-width: 75vw;
      font-size: 1.6em;
      overflow: hidden;
      padding: 10vh 0;
      line-height: 1.4em;
  }
  img.small {
    width: 40%;
  }
}
</style>
