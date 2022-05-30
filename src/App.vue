<template>
  <div id="app" class="container">
    <div class="jumbotron my-5">
      <h1 class="display-2">Fluid jumbotron</h1>
    </div>
    <TodoInput />
    <TodoList />
  </div>
</template>

<script>
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
export default {
  name: "App",
  components: {
    TodoInput,
    TodoList,
  },
};
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
