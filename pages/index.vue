<template>
  <v-layout row>
    <v-flex sm6 offset-sm3 text-xs-center>
      <h1 id="title">TODO LIST</h1>
      <todo-input />
      <todo-list />
    </v-flex>
  </v-layout>
</template>

<script>
import TodoInput from '@/components/TodoInput'
import TodoList from '@/components/TodoList'

export default {
  components: { TodoInput, TodoList },
  async fetch({ store }) {
    await store.dispatch('todos/setTodos')
  }
}
</script>
<style>
#title {
  font-family: 'Avenir', 'Helvetica', 'sans-serif';
  font-weight: 100;
  color: white;
  opacity: 0.8;
  margin: 35px 0;
  letter-spacing: 6px;
  font-size: 40px;
}
.input-group__input {
  padding: 0 !important;
}
</style>
