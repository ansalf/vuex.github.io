<template>
  <div>
    <div class="col">
      <input
        @change="todoTextChange"
        v-bind:value="todoText"
        class="col form-control mx-20"
        type="text"
      />
      <button @click="addTodoI" class="btn btn-primary btn-md" style="margin:5px 5px 5px 5px;">Add</button>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import { v1 } from "uuid";

export default {
  data() {
    return {
      todoText: ""
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
        complete: false
      });
      this.todoText = "";
    }
  }
};
</script>

<style scoped>
</style>