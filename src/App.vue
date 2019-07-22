<template>
  <div id="app">
    <TodoList/>
    <Navbar/>

  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import Navbar from './components/Navbar.vue'

export default {
  name: 'app',
  components: {
    Navbar,
    TodoList
  }
}
</script>

<style lang="scss">
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;
  
}
</style>
