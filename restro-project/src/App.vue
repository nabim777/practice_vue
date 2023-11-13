<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- use that components with props having variable name,msg calls -->
  <HomeSection
    name="Myself Nalem7"
    msg="I am learning Vue JS framework hai ta"
  />
</template>

<script>
//import
import HomeSection from "./components/HomeSection.vue";

// register
export default {
  name: "App",
  components: {
    // HelloWorld,
    HomeSection,
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