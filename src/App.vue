<template>
  <div class="container col-md-8 mt-5">
      <TodoInput />
      <TodoList />
  </div>
</template>

<script>
import TodoInput from '@/components/TodoInput'
import TodoList from '@/components/TodoList'
export default {
  name: 'App',
  components: {
    TodoInput,
    TodoList
  },
  data() {
    return {
      providedData: {
        taskList: [
          {id: 1, text: "Click me!"},
        ]
      }
    }
  },
  provide() {
    return {
      providedData: this.providedData,
    }
  }
}
</script>
