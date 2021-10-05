<template>
  <div id="app">
    <todoListe></todoListe>
  </div>
</template>

<script>
import todoListe from './components/todoListe.vue'

export default {
  name: 'App',
  components: {
    todoListe
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
