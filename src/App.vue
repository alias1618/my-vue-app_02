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
            // header: "Sign up for the Giveaway",
            // text: "Grab you ninja swag for half price",
            showModal: false,
            showModalTwo: false
        };
    },
    methods: {
      toggleModal(){
        this.showModal = !this.showModal
      },
      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
    },
}
</script>

<template>
  <!-- <h1>My first vue App</h1> -->
  <h1>{{ title }}</h1>
  <p>Welcom</p>
  <!-- <input type="text" ref="name"> -->
  <!-- <div v-if="showModal"> -->
  <teleport to=".modals" v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price</p>
    </Modal>
  <!-- </div> -->
  </teleport>

  <teleport v-if="showModalTwo">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal  @close="toggleModalTwo">
      <h1>sign up to the newlwtter</h1>
      <p>For updates and promo codes!</p>
    </Modal>
  </teleport >

  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click="toggleModalTwo">open modal</button>
</template>

<style>
#app, .modals {
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
