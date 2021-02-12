<template>
  <div id="app">
  <h1>Todos</h1>
  <h3>completed: {{ computedTodos }}</h3>
  <h3>pending: {{ pendingTodos }}</h3>
  <todo-list />
    <todo-form />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';
import TodoForm from './components/TodoForm.vue';

export default {
  name: 'App',
  components: {
    TodoList,
    TodoForm,
  },
  computed:{
    computedTodos(){
      return this.$store.getters.computedTodos;
    },

    pendingTodos(){
      return this.$store.getters.pendingTodos;
    }
  }
};
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
