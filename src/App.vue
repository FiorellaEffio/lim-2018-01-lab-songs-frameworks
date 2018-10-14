<template>
  <div id="app">
    <div v-for="artist in artists">
      <Artist :artistName="artist"/>
    </div>
  </div>
</template>

<script>
import Artist from "./components/Artist";

export default {
  name: "App",
  components: {
    Artist
  },
  data : function() {
    return {msg: "holis",
    artists: ['metallica','radiohead']
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
