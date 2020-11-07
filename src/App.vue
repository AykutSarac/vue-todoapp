<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Header from './components/Header';
import Todos from './components/Todos';

let todos = [
  {
    id: "1",
    name: "Complete assignments"
  },
  {
    id: "2",
    name: "Study Vue.js"
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
