<template>
  <div id="app">
    <Containers></Containers>
  </div>
</template>

<script>
import Containers from './components/Containers.vue'

export default {
  name: 'app',
  components: {
    Containers
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.row {
  float: left;
}
</style>
