<template>

  <h1>{{ title }}</h1>
  <p>{{ header }}</p>

  <input type="text" ref="name">
  <button @click.prevent="handleClick">Click me!</button>

  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Hey Ninja :)</h1>
      <p>Grab your swag yeehaw!</p>
      <hr>
      <template v-slot:links>
        <div>
          <h4>Links</h4>
          <a href="#">Sign up</a>  |  <a href="#">Login</a>
        </div>
      </template>
    </Modal>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <Modal theme="sale" @close="toggleModalTwo">
      <h1>Hey Ninja :) Two</h1>
      <p>Grab your swag yeehaw!</p>
      <hr>
      <template v-slot:links>
        <div>
          <h4>Links Two</h4>
          <a href="#">Sign up</a>  |  <a href="#">Login</a>
        </div>
      </template>
    </Modal>
  </teleport>

  <br><br>
  <div>
    <button @click="toggleModal">Open Modal</button>
    <button @click="toggleModalTwo">Open Modal Two</button>
  </div>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "Drew is a fun guy :)",
      header:"Sign up for the Giveaway",
      text: "Grab the giveaway for half price!",
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('reddy')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
  #app, .modals {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .reddy {
    background: rgb(251, 255, 197);
  }
</style>
