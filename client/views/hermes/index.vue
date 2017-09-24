<template>
  <div>
    <div v-if="this.isIn" class="tile is-parent ">
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
    <div v-else>
      <article class="tile is-child box">Please login !</article>
      <button @click="change_login">login</button>
    </div>
  </div>
</template>
<script>
  import myVideo from 'vue-video-module'
  import { Collapse, Item as CollapseItem } from 'vue-bulma-collapse'
  import { mapGetters, mapActions } from 'vuex'

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

    computed: mapGetters({
      isIn: 'isAuthenticated'
    }),
    methods: {
      ...mapActions([
        'loginUser'
      ]),
      change_login () {
        this.loginUser({isAuthenticated: true})
        console.log(this.isIn)
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
