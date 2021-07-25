<template>
  <div id="app">

    <header-component></header-component>

    <main>
      <ul>
        <li>
          <img :src="image" alt="">
          <p>{{ hero.name }}</p>
          <p>Jenis Hero: <em>{{ hero.type }}</em></p>
        </li>
      </ul>
    </main>

    <footer-component></footer-component>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    'header-component': Header,
    'footer-component': Footer
  },
  data: function() {
    return {
      hero: {
        name: 'Aurora',
        type: 'Mage',
        image: 'aurora.jpg'
      }
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
  computed: {
    image: function() {
      return require('./assets/hero/' + this.hero.image)
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
