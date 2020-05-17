<template>
  <div id="app">
  <Header/>
  <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    Header,
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo ONE",
          completed: false
        },
        {
          id: 2,
          title: "Todo TWO",
          completed: true
        },
        {
          id: 3,
          title: "Todo THREE",
          completed: false
        }
      ]
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => this.todos = res.data)
    .catch(err=> console.log(err));
  }
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
