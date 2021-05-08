<template>
  <q-page style="background-color: #ddd">
    <div class="row">
      <div class="col-12 col-lg-6 col-xs-12">
        <div style="width:100%; height:17px; background-color:#ddd; font-size:12px;padding-left:4px;">
          <div class="row">
            <div class="col text-left">
              <a href="https://www.youtube.com/watch?v=7-RhgB1INII" style="text-decoration: none;" target="_blank">Original link</a>
            </div>
            <div class="col text-center text-bold">RUV - Geldingadalir</div>
            <div class="col text-right">
              <q-btn flat size="xs" icon="mdi-circle-expand" style="width:26px; margin-top: -2px;" @click="expand(0)"/>
            </div>
          </div>
        </div>

        <vue-plyr :style="halfheightpx">
          <div class="plyr__video-embed">
            <iframe
              src="https://www.youtube.com/watch?v=7-RhgB1INII?amp;iv_load_policy=3&amp;modestbranding=1&amp;playsinline=1&amp;showinfo=0&amp;rel=0&amp;enablejsapi=1"
              allowfullscreen
              allowtransparency
              allow="autoplay"
              :playsinline="true"
            ></iframe>
          </div>
        </vue-plyr>
      </div>
      <div class="col-12 col-lg-6 col-xs-12 q-pl-xs">
        <div style="width:100%; height:17px; background-color:#ddd; font-size:12px;padding-left:4px;">
          <div class="row">
            <div class="col text-left">
              <a href="https://www.youtube.com/watch?v=BA-9QzIcr3c" style="text-decoration: none;" target="_blank">Original link</a>
            </div>
            <div class="col text-center text-bold">RUV - Langihryggur</div>
            <div class="col text-right">
              <q-btn flat size="xs" icon="mdi-circle-expand" style="width:36px; margin-top: -2px;" @click="expand(1)"/>
            </div>
          </div>
        </div>

        <vue-plyr :style="halfheightpx">
          <div class="plyr__video-embed">
            <iframe
              src="https://www.youtube.com/watch?v=BA-9QzIcr3c?amp;iv_load_policy=3&amp;modestbranding=1&amp;playsinline=1&amp;showinfo=0&amp;rel=0&amp;enablejsapi=1"
              allowfullscreen
              allowtransparency
              allow="autoplay"
              :playsinline="true"
            ></iframe>
          </div>
        </vue-plyr>
      </div>
    </div>
    <div class="row">
      <div class="col-12 col-lg-6 col-xs-12">
        <div style="width:100%; height:17px; background-color:#ddd; font-size:12px;padding-left:4px;">
          <div class="row">
            <div class="col text-left">
              <a href="https://k100streymi.mbl.is/p2p/webcam0" style="text-decoration: none;" target="_blank">Original link</a>
            </div>
            <div class="col text-center text-bold">MBL - Myndavél 1</div>
            <div class="col text-right">
              <q-btn flat size="xs" icon="mdi-circle-expand" style="width:26px; margin-top: -2px;" @click="expand(2)"/>
            </div>
          </div>
        </div>

        <iframe
          width="100%"
          :height="halfheight"
          allow="autoplay"
          frameborder="0"
          src="https://k100streymi.mbl.is/p2p/webcam0">
        </iframe>
      </div>
      <div class="col-12 col-lg-6 col-xs-12 q-pl-xs">
        <div style="width:100%; height:17px; background-color:#ddd; font-size:12px;padding-left:4px;">
          <div class="row">
            <div class="col text-left">
              <a href="https://k100streymi.mbl.is/p2p/webcam1" style="text-decoration: none;" target="_blank">Original link</a>
            </div>
            <div class="col text-center text-bold">MBL - Myndavél 2</div>
            <div class="col text-right">
              <q-btn flat size="xs" icon="mdi-circle-expand" style="width:36px; margin-top: -2px;" @click="expand(3)"/>
            </div>
          </div>
        </div>

        <iframe
          width="100%"
          :height="halfheight"
          allow="autoplay"
          frameborder="0"
          src="https://k100streymi.mbl.is/p2p/webcam1">
        </iframe>
      </div>
    </div>
    <q-dialog
      v-model="dialog"
      persistent
      :maximized="maximizedToggle"
      transition-show="slide-up"
      transition-hide="slide-down"
    >
      <q-card class="bg-primary text-white">
        <q-bar>
          <q-space />
          <q-btn dense flat icon="mdi-window-minimize" @click="maximizedToggle = false" :disable="!maximizedToggle">
            <q-tooltip v-if="maximizedToggle" content-class="bg-white text-primary">Minimize</q-tooltip>
          </q-btn>
          <q-btn dense flat icon="mdi-crop-square" @click="maximizedToggle = true" :disable="maximizedToggle">
            <q-tooltip v-if="!maximizedToggle" content-class="bg-white text-primary">Maximize</q-tooltip>
          </q-btn>
          <q-btn dense flat icon="mdi-close" v-close-popup>
            <q-tooltip content-class="bg-white text-primary">Close</q-tooltip>
          </q-btn>
        </q-bar>
        <q-card-section class="q-pt-none">
          <vue-plyr :style="fullheightpx" v-if="videonr===0">
            <div class="plyr__video-embed">
              <iframe
                src="https://www.youtube.com/watch?v=7-RhgB1INII?amp;iv_load_policy=3&amp;modestbranding=1&amp;playsinline=1&amp;showinfo=0&amp;rel=0&amp;enablejsapi=1"
                allowfullscreen
                allowtransparency
                allow="autoplay"
                :playsinline="true"
              ></iframe>
            </div>
          </vue-plyr>

          <vue-plyr :style="fullheightpx" v-if="videonr===1">
            <div class="plyr__video-embed">
              <iframe
                src="https://www.youtube.com/watch?v=BA-9QzIcr3c?amp;iv_load_policy=3&amp;modestbranding=1&amp;playsinline=1&amp;showinfo=0&amp;rel=0&amp;enablejsapi=1"
                allowfullscreen
                allowtransparency
                allow="autoplay"
                :playsinline="true"
              ></iframe>
            </div>
          </vue-plyr>

          <iframe
            v-if="videonr===2"
            width="100%"
            :height="fullheight"
            frameborder="0"
            src="https://k100streymi.mbl.is/p2p/webcam0">
          </iframe>

          <iframe
            v-if="videonr===3"
            width="100%"
            :height="fullheight"
            allow="autoplay"
            frameborder="0"
            src="https://k100streymi.mbl.is/p2p/webcam1">
          </iframe>      
        </q-card-section>
      </q-card>
    </q-dialog>
  </q-page>
</template>

<script>
import VuePlyr from 'vue-plyr'
export default {
  data () {
    return {
      maximizedToggle: true,
      fullheight: 0,
      halfheight: 0,
      halfheightpx: 0,
      fullheightpx: '',
      dialog: false,
      videonr: 0
    }
  },
  methods: {
    expand (nr) {
      this.videonr = nr
      this.dialog = !this.dialog
    }
  },
  mounted () {
    const h = document.getElementsByClassName('q-page')[0].clientHeight
    console.log(h)
    this.fullheight = h - 65
    this.halfheight = h / 2
    this.fullheightpx = 'height: ' + this.fullheight + 'px'
    this.halfheightpx = 'height: ' + this.halfheight + 'px'
  },
  components: {
    VuePlyr
  }
}
</script>

<style>

</style>