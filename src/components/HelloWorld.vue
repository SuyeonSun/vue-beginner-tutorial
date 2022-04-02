<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <button id="counter" @click="increment">increment</button>
    {{count}}
    <button @click="decrement">decrement</button>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      count : 0,
      someObject: {},
      // handleClick,
    }
  },
  mounted() {
    const newObject = {}
    this.someObject = newObject
    console.log(newObject === this.someObject) // false
    console.log("on mounted!") // false
  },

  // 관심사를 분리한다.
  methods : {
    async increment() {
      this.count++
    },
    decrement() {
      this.count--;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
