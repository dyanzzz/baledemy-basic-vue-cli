<template>
  <ul>
    <li>
      <img :src="image" alt="">
      <p>{{ hero.name }}</p>
      <p>Jenis Hero: <em>{{ hero.type }}</em></p>
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'Hero',
    props: ['hero'],
    computed: {
      image: function() {
        return require('../assets/hero/' + this.hero.image)
      }
    },
  }
</script>

<style scoped>
  p {
    color: salmon;
  }
</style>