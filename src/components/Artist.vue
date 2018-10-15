<template>
  <div class="hello">
    <h1>Artista: '{{ artistName }}'</h1>
    <h2>Songs</h2>
    {{songs[0]}}
    <div v-for="song in songs">
      <Song :songName="song"/>
    </div>
    <button v-on:click="getSongs">Click me to see the artis</button>
  </div>
</template>

<script>
import Song from "./Song";
export default {
  name: "Artist",
  components: {
    Song,
  },
  props: ['artistName'],
  data: function() {
    return {
      msg: "This is my message",
      songs: ['hola']
    }
  },
  methods: {
    getSongs: function() {
      var self = this;
      let urlArtist = 'http://ws.audioscrobbler.com/2.0/?method=artist.gettoptracks&api_key=8cd7c52e092d2a9a7f15b02486b94879&format=json&limit=10&artist=' + this.artistName;
      fetch(urlArtist)
        .then(function(response) {
          return response.json();
        })
        .then(function(myJson) {
          let result = myJson.toptracks.track;
          self.songs = result;
          console.log(result);
        });
    }
  },
  beforeCreated: function () {
    urlArtist = 'http://ws.audioscrobbler.com/2.0/?method=artist.gettoptracks&api_key=8cd7c52e092d2a9a7f15b02486b94879&format=json&limit=10&artist=' + this.artistName;
    fetch(urlArtist)
    .then(res => {
      this.songs = res;
    })
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
