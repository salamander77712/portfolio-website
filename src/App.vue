<script setup>
import ProjectDisplay from './components/ProjectDisplay.vue'
import ProjectContainer from './components/ProjectContainer.vue'
import ProjectSearch from './components/ProjectSearch.vue'
import { provide } from 'vue'
import projectData from './data/projects.json';
import settings from './data/settings.json';
provide('projectData', projectData);
provide('settings', settings);
</script>
<script>
export default {
  data() {
    return {
    }
  },
  created(){
    document.title = 'AHWW';
  }
}
</script>

<template>
  <projectContainer></projectContainer>
</template>

<style scoped>

</style>
