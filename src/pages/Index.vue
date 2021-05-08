<template>
  <q-page>
    <div class="row">
      <div class="col">
        <vue-plyr :style="halfheightpx">
          <div class="plyr__video-embed">
            <iframe
              src="https://www.youtube.com/watch?v=7-RhgB1INII?amp;iv_load_policy=3&amp;modestbranding=1&amp;playsinline=1&amp;showinfo=0&amp;rel=0&amp;enablejsapi=1"
              allowfullscreen
              allowtransparency
              allow="autoplay"
            ></iframe>
          </div>
        </vue-plyr>
      </div>
      <div class="col">
        <vue-plyr>
          <div class="plyr__video-embed">
            <iframe
              src="https://www.youtube.com/watch?v=BA-9QzIcr3c?amp;iv_load_policy=3&amp;modestbranding=1&amp;playsinline=1&amp;showinfo=0&amp;rel=0&amp;enablejsapi=1"
              allowfullscreen
              allowtransparency
              allow="autoplay"
            ></iframe>
          </div>
        </vue-plyr>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <iframe
          width="100%"
          :height="halfheight"
          src="https://k100streymi.mbl.is/p2p/webcam0">
        </iframe>    
      </div>
      <div class="col">
        <iframe
          width="100%"
          :height="halfheight"
          allow="autoplay"
          src="https://k100streymi.mbl.is/p2p/webcam1">
        </iframe>
      </div>
    </div>
  </q-page>
</template>

<script>
import VuePlyr from 'vue-plyr'
export default {
  data () {
    return {
      halfheight: 0,
      halfheightpx: 0
    }
  },
  mounted() {
    console.log('this is current player instance object', this.player)
  },
  mounted () {
    const h = document.getElementsByClassName('q-page')[0].clientHeight - 50
    console.log(h)
    this.halfheight = h / 2
    this.halfheightpx = 'heigh: ' + this.halfheight + 'px'
  },
  methods: {
    // listen event
    onPlayerPlay(player) {
      // console.log('player play!', player)
    },
    onPlayerPause(player) {
      // console.log('player pause!', player)
    },
    // ...player event

    // or listen state event
    playerStateChanged(playerCurrentState) {
      // console.log('player current update state', playerCurrentState)
    },

    // player is ready
    playerReadied(player) {
      console.log('the player is readied', player)
      // you can use it to do something...
      // player.[methods]
    }
  },
  components: {
    VuePlyr
  }
}
</script>

<style>

</style>