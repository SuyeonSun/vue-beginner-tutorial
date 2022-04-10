<template>
<!--<img alt="Vue logo" src="./assets/logo.png">-->
<!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <div>
    <!--선언적 렌더링-->
    <div>{{counter}}</div>

    <!--@click-->
    <div>
      <button @click="reverseMessage">Reverse Message</button>
      {{message}}
    </div>

    <!--v-model -> two-way-binding-->
    <div>
      <input v-model="message2">
      {{message2}}
    </div>

    <!--조건문-->
    <div>
      <span v-if="seen">You can see me now!</span>
    </div>

    <!--v-bind-->
    <div>
      <ol>
        <TodoItem v-for="item in groceryList" v-bind:todo="item" v-bind:key="item.id"></TodoItem>
      </ol>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoItem from "./components/TodoItem";

export default {
  name: 'App',
  components: {
    // HelloWorld
    TodoItem,
  },
  data() {
    return {
      counter: 0,
      message: 'Hello',
      message2: '',
      seen: true,
      groceryList: [
        {id:0, text:'야채'},
        {id:1, text:'소고기'},
        {id:2, text:'망고'},
      ]
    }
  },
  methods: {
    reverseMessage(){
      this.message = this.message.split('').reverse().join('')
    }
  },
  mounted() {
    setInterval(() => {
      this.counter++
    }, 1000)
    console.log("I'm mounted!")
  },
}
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
