<script setup>
import ProjectContainer from './ProjectContainer.vue';
import DropdownSelect from './DropdownSelect.vue';
import projectData from '../data/projects.json';
import settings from '../data/settings.json';
</script>

<script>
export default {
  emits: ['newValue'],
  data() {
    return {
      projectsRaw: projectData,
      projectMetas: [],
      uniqueMetaNames: [],
      hidden: true,
      selectedSearch: ''
    }
  },
  methods: {
    getMetas() { 
      for (let project in this.projectsRaw){
        if(this.projectsRaw[project].meta != undefined){
          this.projectMetas.push(this.projectsRaw[project].meta);
        }
      }
    },
    getUniqueMetas() {
      for (let metaList in this.projectMetas){
        for(let meta in this.projectMetas[metaList]){
          if (!this.deepIncludes(this.uniqueMetaNames, {"name": this.projectMetas[metaList][meta].name, "type": this.projectMetas[metaList][meta].type})) {
            this.uniqueMetaNames.push({"name": this.projectMetas[metaList][meta].name, "type": this.projectMetas[metaList][meta].type});
          }
        }
      }
    },
    deepIncludes(array, element){
      for (let arrayIndex in array ){
        if(element.name == array[arrayIndex].name){
          return true;
        }
      }
      return false;
    },
    updateSelectedSearch(newValue){
      this.selectedSearch = newValue;
      console.log(this.selectedSearch);
    }
  },
  computed: {
    projectsFiltered() {
      return this.projectsRaw
    },
    metasNamesOnly(){
      let output = [];
      for (let meta in this.uniqueMetaNames){
        output.push(this.uniqueMetaNames[meta].name);
      }
      return output;
    }
  },
  created(){
    this.getMetas();
    this.getUniqueMetas();
  }
}
</script>

<template>
<div>
  <ProjectContainer :settings="settings" :projects="projectsFiltered"></ProjectContainer>
</div>
</template>

<style scoped>

</style>
