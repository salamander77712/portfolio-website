<script setup>
import ImgTipButton from './ImgTipButton.vue'
import splashtexts from '../data/splashtexts.json';
</script>
<script>
export default {
  data() {
    return {
      splashtext :  splashtexts[Math.floor(Math.random() * splashtexts.length)]
    }
  },
  created(){
    const splashtext = 'Alexander Wright';
  }
}
</script>

<template>
<h1>Alexander Hamilton Was Wright</h1>
<h2>Software Developer</h2>
<p>{{splashtext}}</p>
<div>
  <ImgTipButton class="button" link="./assets/Alexander Wright.pdf" tooltip="View Resume" img="./assets/placeholder.png"></ImgTipButton>
  <ImgTipButton class="button" link="https://github.com/salamander77712" tooltip="Go to GitHub Profile" img="./assets/GitHub-Mark-32px.png"></ImgTipButton>
  <ImgTipButton class="button" link="https://www.linkedin.com/in/xhw821/" tooltip="Go to LinkedIn Profile" img="./assets/LinkedIn_icon.svg.png"></ImgTipButton>
</div>
</template>

<style scoped>
h1{
  text-align: center;
}
h2{
  text-align: center;
}
@keyframes splashtext{
  from {font-size: 35px;}
  to {font-size: 40px;}
}
p{
  text-align: center;
  color: red;
  position: absolute;
  left: 55%;
  top: 5%;
  transform: rotate(-25deg);
  z-index: 1;
  animation-name: splashtext;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-timing-function: ease-in-out;
}
div{
  margin: auto;
  width: 15%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
