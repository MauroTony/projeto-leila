<template>
  <TempoJuntos/>
  <ScrollBar/>
  <HelloWorld msg="mauro"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ScrollBar from './components/ScrollBar.vue'
import TempoJuntos from './components/TempoJuntos.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ScrollBar,
    TempoJuntos,
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
body {
  background-color: #202A35;
}
</style>
