<template>
  <div class="footer">
    <a href="/">{{ contact.name }}</a>
    <a href="/">{{ contact.phone }}</a>
    <a href="/">{{ contact.email }}</a>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";
import { Contact } from "@/Models/Contact";
import { Prop } from "vue-property-decorator";

export default class Footer extends Vue {
  @Prop() contact!: Contact;
}
</script>

<style lang="scss">
.footer {
  background-color: black;
  height: 200px;
  margin-top: 20%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
}
.contact-div {
  display: flex;
  flex-direction: row;
}
a {
  position: relative;
  text-decoration: none;
  color: white;
  font-size: 1.3rem;
  padding: 5px;
  margin-left: 10px;
}

a:hover {
  color: #1e90ff;
}
a::before {
  content: "";
  position: absolute;
  display: block;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: dodgerblue;
  transform: scaleX(0);
  transition: transform 0.3s ease;
  transform-origin: left;
}
a:hover::before {
  transform: scaleX(1);
}
</style>
