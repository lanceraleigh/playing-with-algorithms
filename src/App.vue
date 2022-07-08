<template>
  <fibSequence v-if="displayfibSequence" />
  <nSquared v-if="displaynSquared" />
</template>

<script>
import fibSequence from "./components/fibSequence.vue";
import nSquared from "./components/nSquared.vue";

export default {
  name: "App",
  data() {
    return {
      displayfibSequence: false,
      displaynSquared: true,
    };
  },
  components: {
    fibSequence,
    nSquared,
  },
};
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
</style>
