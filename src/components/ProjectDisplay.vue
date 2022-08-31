<script setup>
import ImgTipButton from './ImgTipButton.vue';
</script>

<script>
export default {
  props: ["project", 'colors', 'gitImg'],
  data() {
    return {
    }
  }
}
</script>

<template>
<div>
  <h2>{{project.title}}</h2>
  <p>{{project.description}}</p>
  <img :src="project.image" :alt="project.imageAlt">
  <ImgTipButton :link="project.link" :colors="colors" tooltip="View On GitHub" :img="gitImg"></ImgTipButton>
  <slot></slot>
</div>

</template>

<style scoped>
h2{
  color:v-bind(colors[2]);
}
p{
  color:v-bind(colors[2]);
}
div {
  background-color: v-bind(colors[1]);
  padding: 1%;
  margin: 1%;
  float: left;
  width: 46%;
}
img {
  height: 25%;
  width: 25%;
}
@media screen and (max-width: 700px) {
  div {
    width: 100%;
  }
}
</style>
