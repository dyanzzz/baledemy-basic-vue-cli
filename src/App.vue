<template>
  <div id="app">

    <header-component @change-hero="changeHero"></header-component>

    <main>
      <template v-for="item in hero" >
        <hero-component :hero="item" :key="item.id"></hero-component>
      </template>
    </main>

    <footer-component></footer-component>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Hero from './components/Hero.vue'

export default {
  name: 'App',
  components: {
    'header-component': Header,
    'footer-component': Footer,
    'hero-component': Hero
  },
  data: function() {
    return {
      hero: [
        {
          id: 1,
          name: 'Aurora',
          type: 'Mage',
          image: 'aurora.jpg'
        },
        {
          id: 2,
          name: 'Zilong',
          type: 'Figter',
          image: 'zilong.jpg'
        }
      ]
    }
  },
  methods: {
    changeHero: function() {
      this.hero = {
        name: 'Zilong',
        type: 'Figter',
        image: 'zilong.jpg'
      }
    }
  },
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
main img {
  width: 80px;
  border: 1px solid #ccc;
}
</style>
