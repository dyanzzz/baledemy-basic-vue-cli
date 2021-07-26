<template>
  <ul>
    <li>
      <img :src="image" alt="">
      <p>{{ index+1 }}. {{ hero.name }}</p>
      <p>Jenis Hero: <u>{{ hero.type }}</u></p>
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'Hero',
    props: ['hero', 'index'],
    computed: {
      image: function() {
        return require('../assets/hero/' + this.hero.image)
      }
    },
  }
</script>

<style scoped>
  p {
    margin: 0;
  }
  li {
    list-style: none;
  }
</style>