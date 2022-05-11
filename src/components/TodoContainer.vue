<template>
  <div class="main">
    <h1>Todo-list</h1>
    <CreateTodo @createTodo="handleTodo" />
    <ul>
      <li
        class="todo-li"
        :class="{ complete: todo.complete }"
        v-for="(todo, index) in todos"
        :key="index.id"
      >
        {{ todo.description }}
        <div class="btn-div">
          <input type="checkbox" v-model="todo.complete" class="complete" />
          <button class="delete-btn" @click="remove(index)">X</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CreateTodo from "./CreateTodo.vue";
import Footer from "./Footer.vue";
import { Todo } from "@/Models/Todo";

@Options({
  components: {
    CreateTodo,
    Footer,
  },
})
export default class TodoContainer extends Vue {
  todos: Todo[] = [
    new Todo("Träna", true),
    new Todo("Basta", true),
    new Todo("Laga mat", false),
  ];

  handleTodo(t: Todo) {
    console.log("Container log", t);
    this.todos.push(t);
  }

  done() {
    console.log("Done btn log");
  }

  remove(index: number) {
    console.log("Remove btn log", index);

    this.todos.splice(index, 1);
  }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Bangers&family=Bebas+Neue&family=Indie+Flower&family=Inter:wght@400;600&family=Josefin+Sans:wght@100&family=Patrick+Hand&family=Permanent+Marker&display=swap");

ul {
  flex-grow: 1;
  padding: 10px;
}

.todo-li {
  list-style-type: none;
  width: 300px;
  border: 1px solid black;
  display: flex;
  height: 30px;
  border-radius: 5px;
  padding: 5px;
  font-family: "Josefin Sans", sans-serif;
  margin-top: 10px;
  color: black;
  background-color: white;
  background-attachment: scroll;
  font-size: 1.2rem;
}

.btn-div {
  flex-grow: 1;
  display: flex;
  justify-content: flex-end;
  color: black;
}
.complete {
  text-decoration: line-through;
  opacity: 0.8;
}
input.complete {
  width: 20px;
  height: 20px;
  cursor: pointer;
}
.delete-btn {
  width: 20px;
  height: 20px;
  background-color: white;
  cursor: pointer;
  &:hover {
    background-color: black;
    color: white;
  }
}
h1 {
  font-family: "Bebas Neue", cursive;
  text-decoration-line: underline;
  margin-bottom: 20px;
  font-size: 2.5rem;
}
</style>
