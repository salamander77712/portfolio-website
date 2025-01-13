<script setup>
import ProjectDisplay from './components/ProjectDisplay.vue'
import ProjectContainer from './components/ProjectContainer.vue'
import ProjectSearch from './components/ProjectSearch.vue'
import ContactHeader from './components/ContactHeader.vue'
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
    document.title = 'Alexander Wright';
  }
}
</script>

<template>
  <ContactHeader></ContactHeader>
  <h1>Projects</h1>
  <ProjectContainer></ProjectContainer>
</template>

<style scoped>

</style>
