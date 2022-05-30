<template>
  <div>
    <div class="d-flex">
      <input
        @change="todoTextChange"
        v-bind:value="todoText"
        class="form-control mx-2"
        placeholder="Please enter what you need to do"
      />
      <button
        @click="addTodoI(todoText)"
        class="btn btn-outline-primary btn-lg"
      >
        ADD
      </button>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import { v1 } from "uuid";

export default {
  data() {
    return {
      todoText: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    todoTextChange(e) {
      this.todoText = e.target.value;
    },
    addTodoI() {
      this.addTodo({
        id: v1(),
        title: this.todoText,
      });
      this.todoText = "";
    },
  },
};
</script>

<style scoped></style>
