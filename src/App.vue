<template>
  <h1><i>Reaction Timer</i></h1>
  <button @click="start" :disabled="isPlaying"><strong>PLAY</strong></button>
  <block v-if="isPlaying" :delay="delay" />
</template>

<script>
import block from "./components/block.vue";
export default {
  name: "App",
  components: { block },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
