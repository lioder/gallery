<template>
  <div class="photo-wrapper">
    <img class="photo-content" :src="photo.url" width="180px" height="180px" @mouseenter="showDesc = true"
         @mouseleave="showDesc = false">
    <transition name="move">
      <div class="photo-desc" v-show="showDesc">{{ photo.desc }}</div>
    </transition>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      photo: {
        type: Object
      }
    },
    data () {
      return {
        showDesc: false
      }
    }
  }
</script>

<style lang="stylus">
  .photo-wrapper
    display: inline-block
    position: relative
    width: 195px
    height: 198px
    text-align: center
    overflow: hidden
    background-color: #fff
    .photo-content
      padding: 9px 7.5px
    .photo-desc
      position: absolute
      padding: 7.5px 0
      left: 0
      bottom: 0
      height: 25.35px
      width: 100%
      transform: translateY(0)
      background-color: rgba(255, 255, 255, 0.85)
      text-align: center
      font-size: 15px
      color: #6E7799
      &.move-enter-active, &.move-leave-active
        transition: all 0.3s
      &.move-enter, &.move-leave-to
        transform: translateY(25.35px)
        opacity: 0
</style>
