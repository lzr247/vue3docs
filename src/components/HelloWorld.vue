<template>
  <div id="computed-basics">
    <p>Has published books:</p>
    <span>{{ publishedBooksMessage }}</span>
    <p>Full Name:</p>
    <span>{{ fullName }}</span>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return  {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      },
      firstName: 'Lazar',
      lastName: 'Conic'
    }
  },
  computed: {
    publishedBooksMessage() {
      return this.author.books.length > 3 ? 'Yes' : 'No'
    },
    fullName: {
      // getter
      get() {
        return this.firstName + ' ' + this.lastName
      },
      set(newValue) {
        const names = newValue.split(' ')
        this.firstName = names[0]
        this.lastName = names[names.length-1]
      }
    }
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
