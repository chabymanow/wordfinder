<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Thesaurus />
</template>

<script>

import Thesaurus from './components/Thesaurus.vue'

export default {
  name: 'App',
  components: {
    Thesaurus
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
