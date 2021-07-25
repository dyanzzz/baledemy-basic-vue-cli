<template>
  <div id="app">
    <header>
      <img alt="Vue logo" src="./assets/logo.png" width="200">
      <h3>Mobile Legend : Bang bang</h3>
      <button @click="changeHero">Change Hero</button>
    </header>

    <main>
      <ul>
        <li>
          <img :src="image" alt="">
          <p>{{ hero.name }}</p>
          <p>Jenis Hero: <em>{{ hero.type }}</em></p>
        </li>
      </ul>
    </main>

    <footer>
      <p>&copy; 2021 - Kelas Vue CLI</p>
    </footer>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
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
