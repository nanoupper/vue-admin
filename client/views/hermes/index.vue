<template>
  <div>
    <div class="tile is-parent is-4">
      <article class="tile is-child box">
        <h1 class="title">Hermes Lehrvideos</h1>
        <div class="block is-flex">
          <collapse>
            <collapse-item title="Video 1">
              <myVideo ref="video1" :options="videoOptions"></myVideo>
            </collapse-item>
            <collapse-item title="Video 2">
              <myVideo ref="video2" :options="videoOptions"></myVideo>
            </collapse-item>
          </collapse>
        </div>
      </article>
    </div>
  </div>
</template>
<script>
  import myVideo from 'vue-video-module'
  import { Collapse, Item as CollapseItem } from 'vue-bulma-collapse'

  export default {
    components: {
      myVideo,
      Collapse,
      CollapseItem
    },
    data () {
      return {
        videoOptions: {
          src: 'http://vjs.zencdn.net/v/oceans.mp4',
          poster: 'image/2.jpg',
          fullscreen: true
        }
      }
    },
    mounted () {
      this.video1 = this.$refs.video1
      this.video2 = this.$refs.video2
    }
  }
</script>
<style>

</style>
