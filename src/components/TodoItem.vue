<template>
  <div class="d-flex my-3 justify-content-between">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" />
    </div>
    <h3 v-if="!editing" class="col form-check-label">
      {{ todo.title }}
    </h3>
    <input
      v-bind:value="todoText"
      @change="todoTextChange"
      v-else
      type="text"
      class="form-control"
    />
    <button
      @click="updateTodoI(todo)"
      class="btn btn-outline-secondary btn-sm mx-2"
    >
      {{ editing ? "MODIFY" : "EDIT" }}
    </button>
    <button @click="deleteTodo(todo.id)" class="btn btn-outline-danger btn-sm">
      DEL
    </button>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  props: {
    todo: {},
  },
  data() {
    return {
      todoText: "",
      editing: false,
    };
  },
  methods: {
    ...mapActions(["deleteTodo", "updateTodo"]),
    todoTextChange(e) {
      this.todoText = e.target.value;
    },
    updateTodoI(todo) {
      this.editing = this.editing == true ? false : true;
      if (this.editing) {
        this.todoText = todo.title;
        this.updateTodo(todo);
      } else {
        todo.title = this.todoText;
      }
    },
  },
};
</script>

<style scoped></style>
