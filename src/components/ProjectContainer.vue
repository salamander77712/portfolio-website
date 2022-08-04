<script setup>
import ProjectDisplay from './ProjectDisplay.vue'
import projectData from '../data/projects.json'
</script>
<script>
export default {
  data() {
    return {
      colors: ["#8ACB88", "#CAE5FF", "#2E4057", "#ACEDFF", "#697A21"],
      projects: projectData
    }
  }
}
</script>

<template>
  <div class="container">
    <div v-for="project in projectData" :key="project.id">
      <ProjectDisplay :project="project" :colors="colors"></ProjectDisplay>
    </div>
  </div>
</template>

<style>
.container{
  float:left;
  background-color: v-bind(colors[4]);
  width:100%;
  position: absolute;
  left: 0;
}
</style>
