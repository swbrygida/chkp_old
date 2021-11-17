<template id="">
  <div class="counter2">




  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css" integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous">


  <ul>

  <li  @click="dodaj">
  <a href="#">
  <i class="fas fa-angle-double-down"></i>
  </a>
  </li>
  <li>
  <a href="#">
  <i class="">{{clicker}}</i>
  </a>
  </li>
  <li @click="odejmij">
  <a href="#">
  <i class="fas fa-angle-double-up" ></i>
  </a>
  </li>

  </ul>


  </div><!-- koniec counter -->

</template>
<script>
import { TimelineLite, TweenMax, gsap } from 'gsap';

export default {
  props: ['clicker', 'allSections'],
  methods: {
    dodaj() {

      this.$emit('clicker', this.clicker++);
      let numberX = this.clicker;
      let numberXS = numberX -1;
      let numberPS = 'section:nth-child(' + numberXS + ')';
      let numberPN = 'section:nth-child(' + numberX + ')';
      let loader1 = document.querySelector(numberPS)
      let loader2 = document.querySelector(numberPN)
      gsap.to(loader1, { y: '-40%', opacity: 0, display: "none"});
      gsap.from(loader2, 1.6, {delay: 1.6, display: "block", y: '40%', opacity: 0, });
      gsap.to(loader2, 1.6, {delay: 2.6,  display: "block",  backgroundColor: '#000', color: '#fff'});




    },
    odejmij() {
      this.$emit('clicker', this.clicker--);
      let numberXW = this.clicker + 1;
      let numberPW = 'section:nth-child(' + numberXW + ')';
      let numberXWZ = this.clicker;
      let numberPWZ = 'section:nth-child(' + numberXWZ + ')';

      let load = document.querySelector(numberPW);
      let load2 = document.querySelector(numberPWZ);

      gsap.to(load, {y: '100%', opacity: 0, display: "none" });
      gsap.from(load2, 0.6, {delay: 0.6, display: "block", y: '-100%', opacity: 0, });
      gsap.to(load2, 0.6, { delay: 1.6, display: "block",  y: '0', opacity: 1, backgroundColor: '#000', color: '#fff'});



    }
  }
}
</script>
<style scoped>
@media screen  and (orientation: portrait) {
  ul {
  margin: 0 ;
  padding: 1vh 0;
  width: 99vw;
  height: 30vh;
  display: flex;
  position: fixed;
  bottom: 20vh;
  right: 0;
  max-height: 19vw;

  }
}

@media screen  and (orientation: landscape) {
  ul {
  margin: 0 ;
  padding: 1vh 0;
  width: 19vw;
  height: 30vh;
  display: flex;
  position: fixed;
  bottom: 0;
  right: 0;
  max-height: 19vw;

  }
}



ul li {
list-style: none;
margin: 15vh 15px;
width: 10vh;
height: 10vh;
}

ul li a {
  position: relative;
  display: block;
  width: 60px!important;
  height: 60px!important;
  text-align: center;
  line-height: 3px;
  background: #333;
  border-radius: 50%;
  font-size: 30px;
  color: #666;
  transition: .5s;
}

ul li a::before {
content: '';
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
border-radius: 50%;
background: #ffee10;
transition: .5s;
transform: scale(.9);
z-index: -1;
}

ul li a:hover::before {
transform: scale(1.1);
box-shadow: 0 0 15px #ffee10;
}

ul li a:hover {
color: #ffee10;
box-shadow: 0 0 5px #ffee10;
text-shadow: 0 0 5px #ffee10;
}
</style>
