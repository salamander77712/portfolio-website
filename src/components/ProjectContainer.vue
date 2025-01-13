<script setup>
import ProjectDisplay from './ProjectDisplay.vue';
import ImgTipButton from './ImgTipButton.vue';
import { inject } from 'vue'

const projects = inject('projectData');
const settings = inject('settings');
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
  <div class="container">
    <div v-for="project in projects" :key="project.id">
      <ProjectDisplay :project="project" >
      <ImgTipButton v-if="project.secondButton" :link="project.secondLink" :tooltip="project.secondTip" :img="project.secondImage"></ImgTipButton>
      </ProjectDisplay>
    </div>
  </div>
</template>

<style>
.container{
  float:left;
  width:100%;
  position: absolute;
  left: 0;
}
</style>
