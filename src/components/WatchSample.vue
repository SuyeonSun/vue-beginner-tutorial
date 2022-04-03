<template>
  <button @click="handleName">click Me</button>
  {{newName}}
</template>

<script>
export default {
  name: "WatchSample",
  data() {
    return {
      name: '',
      newName: '',
    }
  },
  watch: {
    name: function (newValue, oldValue) {
      // this.newName = newValue + '!';
      console.log("newValue: ",newValue, "oldValue: ",oldValue)
    }
  },
  methods: {
    handleName() {
      this.name = 'monkey' + Math.random();// 값이 변경되었을때만 작동
      // this.name = 'monkey'; // 값이 변경되지 않으면 watch는 작동하지 않음
    }
  },
}
</script>

<style scoped>

</style>