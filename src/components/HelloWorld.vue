<template>
  <div>
    {{selected}}
    <select v-model="selected" multiple>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
  </div>
  <div>
    <select v-model="selected2">
      <option v-for="option in options" :key="option" :value="option.value">
        {{option.text}}
      </option>
    </select>
    {{selected2}}
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      selected: '',
      selected2: '',
      options: [
        {text: 'One', value: 'A'},
        {text: 'Two', value: 'B'},
        {text: 'Three', value: 'C'},
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
