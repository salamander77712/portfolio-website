<script setup>
import ProjectDisplay from './ProjectDisplay.vue';
import projectData from '../data/projects.json';
</script>
<script>
export default {
  props: ['settings'],
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
      <ProjectDisplay :project="project" :colors="this.settings.colors" :gitImg="this.settings.gitImg"></ProjectDisplay>
    </div>
  </div>
</template>

<style>
.container{
  float:left;
  background-color: v-bind(settings.colors[4]);
  width:100%;
  position: absolute;
  left: 0;
}
</style>
