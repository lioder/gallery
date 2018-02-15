<template>
  <div id="app">
    <header class="header">
      <nav>
        <div class="logo">
          <img class="logo" src="./common/logo.png" width="40px" height="40px">
        </div>
        <span class="title">Time Lapse</span>
        <ul class="menu">
          <li class="list-item home"><a href="/">Home</a></li>
          <li class="list-item archives"><a href="/archives/">Archives</a></li>
          <li class="list-item projects"><a href="/project/">Projects</a></li>
          <li class="list-item gallery"><a class="active" href="/gallery/">Gallery</a></li>
          <li class="list-item about"><a href="/about/">About</a></li>
        </ul>
      </nav>
    </header>
    <div class="photos">
      <photo class="photo" v-for="(photo,index) in photos" :photo="photo" :key="index"></photo>
    </div>
    <footer class="footer"><a href="http://lioder.top">© 2016-2018   Kry · L</a></footer>
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

<style lang="stylus">
  @import "../static/css/reset.css";

  #app
    width: 100%
    height: 100%
    font-family: "PingFang SC", "Microsoft YaHei", STHeiti, "WenQuanYi Micro Hei", Helvetica, Arial, sans-serif
    -webkit-font-smoothing: antialiased
    -moz-osx-font-smoothing: grayscale
    background-color: #e1f9e7
    color: #1E222E
    .header
      position: fixed
      top: 0
      left: 0
      z-index: 200
      width: 100%
      height: 60px
      line-height: 60px
      background: rgba(255, 255, 255, 0.98)
      box-shadow: 0 0 3px rgba(14, 14, 14, 0.26)
      nav
        padding: 0 80px
        @media(max-width: 710px)
          text-align: center
        .logo
          display: inline-block
          padding-top: 5px
          margin-right: 5px
        .title
          display: inline-block
          transform: translateY(-9px)
          line-height: 10px
          font-size: 26px
          color: #4f8b78
        .menu
          float: right
          @media(max-width: 710px)
            display: none
            opacity: 0
          .list-item
            display: inline-block
            margin: 0 8px
            a
              font-size: 14px
              color: #34495e
              padding-bottom: 4px
              &:hover
                color: #42b983
              &.active
                border-bottom: 3px solid #42b983
    .photos
      display: flex
      flex-wrap: wrap
      justify-content: center
      padding: 100px 200px 0 200px
      @media(max-width: 800px)
        padding-right: 50px
        padding-left: 50px
      .photo
        transform: translateX(10px)
        flex: 0 0 auto
        height: 198px
        width: 195px
        margin-bottom: 20px
        margin-right: 20px
    .footer
      padding: 30px 0
      text-align: center
      line-height: 24px
      a
        color: #2a3e31
</style>
