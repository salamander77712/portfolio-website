<script>
export default {
  props: ['name', 'data'],
  emits: ['newValue'],
  data() {
    return {
      selected: ''
    }
  }
}
</script>

<template>
<select name="metaType" id="metaType" v-model="selected" @onchange="$emit('newValue', this.selected)">
  <option v-for="datum in this.data" :key="datum" :value="datum">{{datum}}</option>
</select>
</template>

<style scoped>

</style>
