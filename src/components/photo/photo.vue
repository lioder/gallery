<template>
  <div class="photo-wrapper">
    <img :src="photo.url">
    <div>{{ photo.desc }}</div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      photo: {
        type: Object
      }
    }
  }
</script>

<style lang="stylus">

</style>
