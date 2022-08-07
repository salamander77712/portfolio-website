<script setup>
import ProjectDisplay from './components/ProjectDisplay.vue'
import ProjectContainer from './components/ProjectContainer.vue'
import settingsData from './data/settings.json'
</script>
<script>
export default {
  data() {
    return {
      settings: settingsData
    }
  }
}
</script>

<template>
  <ProjectContainer :colors="this.settings.colors"></ProjectContainer>
</template>

<style scoped>

</style>
