<script>
export default {
  props: ['link', 'colors'],
  data() {
    return {
    }
  }
}
</script>

<template>
  <span class='tooltip'>
    <a :href="this.link">
    <img src="../assets/GitHub-Mark-32px.png">
    </a>
    <p class='tooltiptext'>View on GitHub</p>
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
