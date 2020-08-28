<template>
  <div id="app">
    <intro v-if="intro" firstName="Arvydas"/>
    <loan v-else/>
  </div>
</template>

<script>
import intro from "./components/intro";
import loan from "./components/loan";
export default {
  name: "App",
  components: {
    intro,
    loan
  },
  created() {
    console.log(this.$store);
  },
  computed: {
    intro() {
      return this.$store.state.showIntro;
    }
  }
};
</script>

<style>
#app {
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
