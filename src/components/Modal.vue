<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{sale:theme === 'sale'}">
      <slot></slot>
      <slot name="links"></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Modal',
    props: [
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
    /* cursor: pointer; */
  }

  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,.5);
    width: 100vw;
    height: 100vh;
  }

  .sale{
    background: hsl(191, 50%, 94%);
  }


</style>
