<script setup>
import { inject } from 'vue'

const settings = inject('settings');
</script>

<script>
export default {
  props: ['link', 'tooltip', 'img'],
  data() {
    return {
    }
  }
}
</script>

<template>
  <span class='tooltip'>
    <a :href="link" target="_blank">
    <img :src="img">
    </a>
    <p class='tooltiptext'>{{tooltip}}</p>
  </span>
</template>

<style scoped>
a{
  float: none;
}
a:hover{
  opacity: 0.5;
}
.tooltip {
  position: relative;
  display: inline-block;
}
.tooltip .tooltiptext {
  visibility: hidden;
  width: 120px;
  background-color: v-bind(settings.colors[2]);
  color: v-bind(settings.colors[1]);
  text-align: center;
  padding: 5px 0;
  border-radius: 6px;
  position: absolute;
  margin-left: -40px;;
  top: 65%;
}
.tooltip:hover .tooltiptext{
  visibility: visible;
}
</style>
