<template>
  <div id="app">
    <LeftRightSide/>
  </div>
</template>

<script>
import LeftRightSide from './components/LeftRightSide'

export default {
  name: 'App',
  components: {
    LeftRightSide
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
</style>
