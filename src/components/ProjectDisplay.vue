<script setup>
import ImgTipButton from './ImgTipButton.vue';
import { inject } from 'vue'

const settings = inject('settings');
</script>

<script>
export default {
  props: ["project"],
  data() {
    return {
    }
  }
}
</script>

<template>
<div>
  <h2>{{project.title}}</h2>
  <img :src="project.image" :alt="project.imageAlt">
  <p>{{project.description}}</p>
  <br>
  <ImgTipButton :link="project.link" tooltip="View On GitHub" :img="settings.gitImg"></ImgTipButton>
  <slot></slot>
</div>

</template>

<style scoped>
h2{
  color:v-bind(settings.colors[2]);
}
p{
  color:v-bind(settings.colors[2]);
}
div {
  background-color: v-bind(settings.colors[1]);
  padding: 1%;
  margin: 1%;
  float: left;
  width: 15%;
  border-radius: 25px;
}
img {
  height: 45%;
  width: 45%;
  border-radius: 15px;
}
@media screen and (max-width: 1300px) {
  div {
    width: 32%;
  }
}
@media screen and (max-width: 700px) {
  div {
    width: 100%;
  }
}
</style>
