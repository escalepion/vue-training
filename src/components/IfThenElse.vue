<template>
  <div>
    <h1>If Then Else</h1>
    <p v-if="ok">This will appear if "ok" is true</p>
    <h4 v-else>This will appear if "ok" is false</h4>
  </div>
</template>
 
<script>
  export default {
    data() {
      return {
        ok: false
      }
    }
  }
</script>