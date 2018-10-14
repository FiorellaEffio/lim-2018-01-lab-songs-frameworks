<template>
  <div class="hello">
    <h1>Artista: '{{ artistName }}'</h1>
    <h2>Songs</h2>
    <button v-on:click="getArtistSongs">Click me to see the artis</button>
  </div>
</template>

<script>
export default {
  name: "Artist",
  props: ['artistName'],
  data: function() {
    return {msg: "This is my message"}
  },
  methods: {
    getArtistSongs: function() {
      let urlArtist = 'http://ws.audioscrobbler.com/2.0/?method=artist.gettoptracks&api_key=8cd7c52e092d2a9a7f15b02486b94879&format=json&limit=10&artist=' + this.artistName;
      fetch(urlArtist)
        .then(function(response) {
          return response.json();
        })
        .then(function(myJson) {
          alert(myJson);
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
