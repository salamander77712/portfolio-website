<script setup>
import ProjectDisplay from './components/ProjectDisplay.vue'
import ProjectContainer from './components/ProjectContainer.vue'
import settingsData from './data/settings.json'
</script>
<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<template>
  <ProjectContainer :settings="this.settingsData"></ProjectContainer>
</template>

<style scoped>

</style>
