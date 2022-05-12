<template>
  <TodoContainer />
  <Footer :contact="me" />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Footer from "./components/Footer.vue";
import TodoContainer from "./components/TodoContainer.vue";
import { Contact } from "./Models/Contact";

@Options({
  components: {
    TodoContainer,
    Footer,
  },
})
export default class App extends Vue {
  me: Contact = new Contact(
    "Malcolm Lindberg",
    29291821728,
    "Malcolm.lindberg@hotmail.se"
  );
}
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
  min-height: 100%;
}

#app {
  height: 100vh;
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
  box-sizing: padding-box;

  .container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}

@media screen and (max-width: 1024px) {
  .main {
    height: 80%;
    margin-top: 0%;
  }
  .footer {
    margin-top: 10%;
    bottom: 0;
  }
  .contact-div {
    width: 30%;
  }
}

@media screen and (max-width: 710px) {
  .main {
    width: 100%;
    margin: 0%;
    overflow: auto;
    background-attachment: fixed;
    background-repeat: auto;
  }
  .footer {
    margin-top: 0%;
  }
  .contact-div {
    width: 50%;
  }
}
</style>
