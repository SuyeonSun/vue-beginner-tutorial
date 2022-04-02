<template>
  {{publishedBooksMessage}}
  <button @click="setPublishedBooksMessage">set publishedBooksMessage</button>
  {{author.books}}
  <br/>
  <button @click="giveFullName">change name</button>
  <br/>
  <!-- get fullName -->
  {{fullName}}
</template>

<script>
export default {
  name: "ComputedSample",
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      },
      firstName: 'John',
      lastName: 'Doe',
    }
  },
  watch: {

  },
  methods: {
    setPublishedBooksMessage() {
      console.log(this.author.books) // get
      this.publishedBooksMessage = []
      // this.author.books = ['changed book']
    },
    giveFullName() {
      // 암시적으로

      // get fullName
      console.log(this.fullName);

      // set value of fullName
      this.fullName = "Hi Sun";

      // get fullName after set
      console.log(this.fullName);

    }
  },
  computed: {
      // publishedBooksMessage() {
      //   return this.author.books.length > 0 ? 'yes' : 'no'
      // },
    publishedBooksMessage: {
      get() {
          return this.author.books.length > 0 ? 'yes' : 'no'
      },
      set(newValue) {
          this.author.books.length = newValue
      }
    },

    fullName: {
      // getter
      get() {
        return this.firstName + ' ' + this.lastName
      },
      // setter
      set(newValue) {
        console.log("set computed: ",newValue);
        [this.firstName, this.lastName] = newValue.split(' ');
      }
    },
  }
}
</script>

<style scoped>

</style>