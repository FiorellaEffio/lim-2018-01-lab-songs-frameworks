<template>
  <div id="app">
    <img src="./assets/logo.png">
    <ul>
      <li v-for="artist in artistsArray">{{ artist }}
      </li>
    </ul>
    <ArtistGeneral/>
    <ArtistGeneral/>
  </div>
</template>

<script>
import ArtistGeneral from './components/ArtistGeneral'

export default {
  name: 'App',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      artistsArray: ['metallica', 'coldplay', 'sia', 'radiohead', 'the+strokes']
    }
  },
  components: {
    ArtistGeneral
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
