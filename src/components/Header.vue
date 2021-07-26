<template>
  <header>
    <img alt="Vue logo" src="../assets/logo.png" width="100">
      <h3>Mobile Legend : Bang bang</h3>
      <button @click="$emit('change-hero')">Random Hero</button>
  </header>
</template>>

<script>
  export default {
    name: 'Header',
    
  }
</script>

<style scoped>

</style>