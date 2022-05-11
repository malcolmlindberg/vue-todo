<template>
  <div class="container">
    <form @submit.prevent="onSubmit">
      <input
        class="text-input"
        type="text"
        placeholder="Write todo here.."
        v-model="todoItem"
      />
      <input class="add-btn" type="submit" value="Add" @click="handleClick" />
    </form>
  </div>
</template>

<script lang="ts">
import { Prop } from "vue-property-decorator";
import { Vue } from "vue-class-component";
import { Todo } from "@/Models/Todo";
export default class CreateTodo extends Vue {
  // @Prop() todos!: [];

  todoItem = "";

  handleClick() {
    if (this.todoItem.trim().length == 0) {
      return;
    }

    console.log("det funkar", this.todoItem);
    this.$emit("createTodo", new Todo(this.todoItem, true));
    this.todoItem = "";
  }
}
</script>

<style lang="scss">
.text-input {
  font-family: "Josefin Sans", sans-serif;
  height: 30px;
  width: 270px;
  color: black;
  outline: none;
  border: 1px solid black;
  font-size: 1.2rem;
}
.add-btn {
  font-family: "Josefin Sans", sans-serif;
  height: 30px;
  color: black;
  border: 1px solid black;
  border-radius: 2px;
  background-color: white;
  padding: 2px;
  font-size: 1.2rem;

  cursor: pointer;
  &:hover {
    background-color: black;
    color: white;
  }
}
</style>
