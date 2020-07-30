<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <TodoList :list="list" @add-todo="addTodo" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  },
  data() {
    return {
      list: [{ value: 'Hello', id: 1},
      { value: 'Hello ererer', id: 2}, 
      { value: 'Hello343434', id: 3}]
    }
    
  },
  methods: {
    addTodo(data) {
      console.log('Add todo : ', data);
      this.list = [...this.list, {
                    id: Math.random(),
                    value: data
                }]
    }
  }
}
</script>

<style>
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI",
  "Roboto", "Oxygen", "Ubuntu", "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji",
  "Segoe UI Emoji", "Segoe UI Symbol";
}
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
