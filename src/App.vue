<template>
  <div class="home">
    <input type="text" v-model="test2">
    <HelloWorld/>
  </div>
</template>

<script>
import {Options, Vue} from 'vue-class-component';
import HelloWorld from './components/HelloWorld.vue'

@Options({
  provide() {
    return {
      test: this.test2,
    };
  },
  data() {
    return {
      test2: "etst2",
    };
  },
  components: {
    HelloWorld
  }
})

export default class Test extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
