<template>
  <GamePlace />
</template>

<script>
import GamePlace from './components/GamePlace.vue'

export default {
  name: 'App',
  components: {
    GamePlace
  },
  data() {
    return {
      
    }
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
  margin: 0 auto;
  width: 195px;
}
</style>
