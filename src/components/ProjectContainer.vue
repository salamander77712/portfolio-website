<script setup>
import ProjectDisplay from './ProjectDisplay.vue';
import ImgTipButton from './ImgTipButton.vue';
</script>
<script>
export default {
  props: ['settings', 'projects'],
  data() {
    return {
    }
  }
}
</script>

<template>
  <div class="container">
    <div v-for="project in projects" :key="project.id">
      <ProjectDisplay :project="project" :colors="settings.colors" :gitImg="settings.gitImg">
      <ImgTipButton v-if="project.secondButton" :colors="settings.colors" :link="project.secondLink" :tooltip="project.secondTip" :img="project.secondImage"></ImgTipButton>
      </ProjectDisplay>
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
