<template>
  <div class="hello">
    <p>Canciones</p>
    <SongArtistComponent/>
    <SongArtistComponent/>
    <SongArtistComponent/>
  </div>
</template>

<script>
import SongArtistComponent from './SongArtistComponent';

export default {
  name: 'ArtistSongsRanking',
  components: {
    SongArtistComponent
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
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
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
