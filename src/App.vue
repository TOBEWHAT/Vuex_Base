<template>
  <div id="app"
       class="container">
    <AddTodo />
    <FilterTodo />
    <Todos></Todos>
  </div>
</template>

<script>
import store from './store'
import AddTodo from './components/AddTodo.vue'
import FilterTodo from './components/FilterTodo.vue'
import Todos from './components/Todos.vue'

export default {
  name: 'App',
  store,
  components: {
    AddTodo,
    Todos,
    FilterTodo
  }
}
</script>

<style>
.container {
  width: 1200px;
  margin: 0 auto;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
