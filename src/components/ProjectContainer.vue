<script setup>
import ProjectDisplay from './ProjectDisplay.vue'
import projectData from '../data/projects.json'
</script>
<script>
export default {
  props: ['colors'],
  data() {
    return {
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
