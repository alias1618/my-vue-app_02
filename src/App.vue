<script >
import { def } from '@vue/shared';
//import { modal } from ".components/Modal.vue";
import Modal from "./components/Modal.vue";

  export default{
    name: "App",
    component: { Modal },
    data() {
        return {
            title: "My first Vue App :)"
        };
    },
    methods: {
        handleClick() {
            console.log(this.$refs.name);
            this.$refs.name.classList.add("active");
            this.$refs.name.focus();
        }
    },
    components: { Modal }
}
</script>

<template>
  <!-- <h1>My first vue App</h1> -->
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
  <Modal />
</template>

<style>
/* .logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
} */
#app {
  font-family: Avenir, Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 5px solid #add;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
