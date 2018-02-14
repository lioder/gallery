<template>
  <div id="app">
    <photo :photo="photos[0]"></photo>
  </div>
</template>

<script>
  import photo from './components/photo/photo.vue'

  const photos = require('./common/photos.json')
  export default {
    name: 'App',
    data () {
      return {
        photos: photos
      }
    },
    components: {
      photo
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
