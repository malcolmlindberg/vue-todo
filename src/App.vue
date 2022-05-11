<template>
  <TodoContainer />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import TodoContainer from "./components/TodoContainer.vue";

@Options({
  components: {
    TodoContainer,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Bangers&family=Bebas+Neue&family=Indie+Flower&family=Inter:wght@400;600&family=Josefin+Sans:wght@100&family=Patrick+Hand&family=Permanent+Marker&display=swap");
* {
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}
body {
  background-image: url(@/assets/pic.jpg);
  background-repeat: no-repeat;
}

.main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 20px 20px;
  background-color: #e9d8a6e4;
  border-radius: 5px;
  margin-top: 150px;
  background-attachment: fixed;
  width: 50%;
  height: 400px;
  margin-left: 25%;
  overflow: scroll;
  background-attachment: scroll;
  background-repeat: auto;
}
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
