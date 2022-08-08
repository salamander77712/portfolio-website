<script>
export default {
  props: ['link', 'colors', 'tooltip', 'img'],
  data() {
    return {
    }
  }
}
</script>

<template>
  <span class='tooltip'>
    <a :href="this.link" target="_blank">
    <img :src="this.img">
    </a>
    <p class='tooltiptext'>{{this.tooltip}}</p>
  </span>
</template>

<style scoped>
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
  background-color: v-bind(colors[2]);
  color: v-bind(colors[1]);
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
