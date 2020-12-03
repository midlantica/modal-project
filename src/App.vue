<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name">
  <button @click.prevent="handleClick">Click me!</button>

  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>

  <br><br>
  <div>
    <button @click="toggleModal">Open Modal</button>
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
      showModal: false
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
    }
  }
}
</script>

<style>
  #app {
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
