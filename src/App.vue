<template>
  <div id="app">
    <UrlGoogleTransform />
  </div>
</template>

<script>
import UrlGoogleTransform from './components/UrlGoogleTransform.vue'

export default {
  name: 'app',
  components: {
    UrlGoogleTransform
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
