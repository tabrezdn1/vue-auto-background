<template>
  <div id="app">
    <AutoBackground ref="autoBackground" :auto="true" :refresh="500">
      <h1>Hello I am slot</h1>
    </AutoBackground>
    <button @click="updateBackground()">Update</button>
  </div>
</template>

<script>
import AutoBackground from "./components/AutoBackground.vue";

export default {
  name: "App",
  components: {
    AutoBackground,
  },
  methods: {
    updateBackground() {
      this.$refs.autoBackground.updateBackground();
    },
  },
};
</script>
<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
