<template>
  <div>
    <h1>Computed Properties</h1>
    <h3>Reverse the word with computed value : </h3>
    <p>{{ helloWorldMessage }}</p>
    <p>{{ reverseMessage }}</p>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        helloWorldMessage: 'Computed Properties'
      }
    },

    computed: {
      reverseMessage: function () {
        return this.helloWorldMessage.split('').reverse().join('');
      }
    }
  }
</script>
