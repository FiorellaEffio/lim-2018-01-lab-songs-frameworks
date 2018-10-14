<template>
  <div class="hello">
    <h3>{{ songName }}</h3>
    <button>Like</button>
    <button>Dislike</button>
  </div>
</template>

<script>
export default {
  name: "Song",
  props: ["artistName"],
  data: function() {
    return { msg: "This is my message" };
  },
  methods: {
    consoleArtistName: function() {
      alert(this.artistName);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
