<template>
  <div id="app">

    <header-component @change-hero="changeHero"></header-component>

    <main>
      <p>Hero-hero terbaik minggu ini</p>
      <article v-if="!selectedHero">
        <template v-for="(item, index) in hero" >
          <hero-component :hero="item" :key="item.id" :index="index"></hero-component>
        </template>
      </article>
      <article v-else>
        <hero-component :hero="selectedHero" :index="0"></hero-component>
      </article>
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
        },
        {
          id: 3,
          name: 'Akai',
          type: 'Tank',
          image: 'akai.jpg'
        },
        {
          id: 4,
          name: 'Bruno',
          type: 'Marksman',
          image: 'bruno.jpg'
        },
        {
          id: 5,
          name: 'Layla',
          type: 'Marksman',
          image: 'layla.jpg'
        },
        {
          id: 6,
          name: 'Lolita',
          type: 'Marksman',
          image: 'lolita.jpg'
        },
        {
          id: 7,
          name: 'Roger',
          type: 'Marksman',
          image: 'roger.jpg'
        },
        {
          id: 8,
          name: 'Nana',
          type: 'Marksman',
          image: 'nana.png'
        },
        {
          id: 9,
          name: 'Lapulapu',
          type: 'Marksman',
          image: 'lapulapu.jpg'
        }
      ],
      selectedHero: ''
    }
  },
  methods: {
    changeHero: function() {
      this.selectedHero = this.randomHero()
    },
    randomHero: function() {
      return this.hero[Math.floor(Math.random() * this.hero.length)]
    }
  },
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
main img {
  width: 80px;
  border: 1px solid #ccc;
}
article {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

main {
  text-align: center ;
}
</style>
