<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{sale:theme === 'sale'}">
      <h1>{{header}}</h1>
      <p>{{text}}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Modal',
    props: [
      'header',
      'text',
      'theme'
    ],
    methods: {
      closeModal() {
        !this.$emit('close')
      }
    }

  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .modal {
    width: 25rem;
    padding: 2rem;
    margin: 5rem auto;
    background: white;
    border-radius: .25rem;
    box-shadow: 0px 2px 12px 2px hsl(0deg 0% 0% / 45%);
    cursor: pointer;
  }

  .backdrop {
    top: 0;
    left: 0;
    position: fixed;
    background: rgba(0,0,0,.5);
    width: 100vw;
    height: 100vh;
  }

  .sale{
    background: rgb(245, 245, 255);
  }
</style>
