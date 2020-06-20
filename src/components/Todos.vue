<template>
  <div class="example">
    <h3>Todos</h3>
    <div class="todos">
      <div class="todo"
           :class="{'is-complete':todo.completed}"
           @dblclick="switchCompleted(todo)"
           v-for="todo in todos"
           :key="todo.id">
        {{todo.title}}
        <span class="closeicon"
              @click="deleteTodo(todo.id)">X</span>
      </div>
    </div>
  </div>

</template>

<script>
import { mapGetters, mapActions } from 'vuex';
export default {
  name: 'Todos',
  computed: mapGetters({
    todos: "getAllTodos"
  }),
  methods: {
    ...mapActions(["getAllTodos", "deleteTodo", "updateTodo"]),
    switchCompleted (todo) {
      const updateTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      }
      this.updateTodo(updateTodo)
    }
  },
  created () {
    this.getAllTodos()
  }
}
</script>

<style scoped>
body {
  background: #ccc;
}
.todos {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
}
.todo {
  background: #41b883;
  padding: 10px;
  border: 1px solid #41b883;
  border-radius: 5px;
  position: relative;
  color: white;
  cursor: all-scroll;
}
.closeicon {
  position: absolute;
  width: 20px;
  height: 20px;
  line-height: 20px;
  top: -10px;
  right: -10px;
  display: block;
  color: fff;
  border: 1px #fff solid;
  border-radius: 50%;
  background: #000;
  cursor: pointer;
  z-index: 100;
  font-size: 12px;
}
.is-complete {
  background: #000;
}
</style>