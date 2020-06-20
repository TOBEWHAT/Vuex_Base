<template>
  <div>
    <h3>Filter todo</h3>
    <select v-model="limit"
            @change="filterTodos(limit)">
      <option value="200">200</option>
      <option value="100">100</option>
      <option value="50">50</option>
      <option value="20">20</option>
      <option value="10">10</option>
      <option value="5">5</option>
    </select>
  </div>
</template>

<script>
// import { mapActions } from 'vuex' //假设不用mapActions
export default {
  name: "FilterTodo",
  data () {
    return {
      limit: 100
    }
  },
  // methods: mapActions(['filterTodos']) //假设不用mapActions
  methods: {
    filterTodos (limit) {
      this.$store.dispatch('filterTodos', limit) //这是第二种方式
    }
  }
}
</script>

<style scoped>
</style>