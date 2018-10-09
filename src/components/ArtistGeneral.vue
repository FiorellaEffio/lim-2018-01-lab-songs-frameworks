<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{ name }}</p>
    <button v-on:click="rankingMetallica">Show results</button>
    <ArtistSongsRanking/>
  </div>
</template>

<script>
import ArtistSongsRanking from './ArtistSongsRanking'

export default {
  name: 'ArtistGeneral',
  components: {
    ArtistSongsRanking
  },
  data () {
    return {
      msg: 'Bienvenida a Ranking de canciones',
      name: 'Fiorella'
    }
  },
  methods: {
    rankingMetallica : function() {
      fetch('http://ws.audioscrobbler.com/2.0/?method=artist.gettoptracks&limit=10&artist=metallica&api_key=8cd7c52e092d2a9a7f15b02486b94879&format=json')
        .then(function(response) {
          return response.json();
        })
        .then(function(myJson) {
          console.log(myJson.toptracks.track);
        });
    },
    getArtistInfo : function() {
      fetch('http://ws.audioscrobbler.com/2.0/?method=artist.getinfo&artist=metallica&api_key=8cd7c52e092d2a9a7f15b02486b94879&format=json')
        .then(function(response) {
          return response.json();
        })
        .then(function(myJson) {
          console.log(myJson.toptracks.track);
        });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
