<template>
  <div class="hello">
    {{ songName.name }}
    <button>Like</button>
    <button>Dislike</button>
  </div>
</template>

<script>
export default {
  name: "Song",
  props: ["songName"],
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
