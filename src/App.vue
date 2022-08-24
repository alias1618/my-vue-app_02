<script >
import { def } from '@vue/shared';
//import { modal } from ".components/Modal.vue";
import Modal from "./components/Modal.vue"


  export default{
    name: "App",
    components: { Modal, Modal },
    data() {
        return {
            title: "My first Vue App :)",
            header: "Sign up for the Giveaway",
            text: "Grab you ninja swag for half price",
            showModal: false
        };
    },
    methods: {
      toggleModal(){
        this.showModal = !this.showModal
      }
    },
}
</script>

<template>
  <!-- <h1>My first vue App</h1> -->
  <h1>{{ title }}</h1>
  <p>Welcom</p>
  <!-- <input type="text" ref="name"> -->
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price</p>
    </Modal>
  </div >
  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click.shift="toggleModal">open modal (shift)</button>
  <button @click.right="toggleModal">open modal (right)</button>
</template>

<style>
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
