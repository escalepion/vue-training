<template>
  <div>
    <h1>Classes and styles</h1>
    <h3>Setting classes with v-bind: class</h3>
    <button @click="toggleActive">Toggle Active</button>
    <button @click="toggleDanger">Toggle Danger</button>
    <p class="defaulClass" v-bind:class="[isActive && 'active' , isDanger && styles.danger, styles.staticClass]">This will take classes</p>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isActive: false,
        isDanger: false,
        styles: {
          active: 'active',
          danger: 'danger',
          staticClass: 'staticClass'
        }
      };      
    },

    methods: {
      toggleActive: function () { this.isActive = !this.isActive; },
      toggleDanger: function () { this.isDanger = !this.isDanger; }
    }
  }
</script>

<style scoped>
  .active {
    color: yellow
  }

  .danger {
    color: red
  }

  .staticClass {
    background-color: blue
  }
</style>

