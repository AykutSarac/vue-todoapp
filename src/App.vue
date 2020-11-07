<template>
  <div id="app">
    <Header v-on:createtodo="createtodo" />
    <Todos v-bind:todos="todos" v-on:deletetodo="deletetodo" />
  </div>
</template>

<script>
import Header from './components/Header';
import Todos from './components/Todos';

let todos = [
  {
    id: "1",
    name: "Complete assignments",
    done: false
  },
  {
    id: "2",
    name: "Study Vue.js",
    done: true
  }
]

export default {
  name: 'App',
  components: {
    Header,
    Todos
  },
  data() {
    return {
      todos
    }
  },
  methods: {
    createtodo: function (todo) {
      let todoObject = {
        id: `${Math.floor(Math.random() * 1000000)}`,
        name: todo,
        done: false
      }

      this.todos.push(todoObject);
    },
     deletetodo: function (id) {
       this.todos = this.todos.filter(todo => todo.id != id);
     }
  }
}
</script>

<style lang="scss">

body {
  margin: 0;
  padding: 0;
  background-image: url('https://images.pexels.com/photos/844297/pexels-photo-844297.jpeg');
  background-position: center center;
  background-attachment: fixed;
  background-size: cover;
  background-repeat: no-repeat;
}


</style>
