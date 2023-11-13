<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- use that components -->
  <HomeSection />
  <!-- reused -->
  <HomeSection />
  
</template>

<script>

//import
import HomeSection from './components/HomeSection.vue'

// register
export default {
  name: 'App',
  components: {
    // HelloWorld,
    HomeSection
  }
}
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