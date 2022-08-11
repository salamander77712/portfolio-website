<script setup>
import ProjectDisplay from './components/ProjectDisplay.vue'
import ProjectContainer from './components/ProjectContainer.vue'
import ProjectSearch from './components/ProjectSearch.vue'
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
  <ProjectSearch :settings="this.settingsData"></ProjectSearch>
</template>

<style scoped>

</style>
