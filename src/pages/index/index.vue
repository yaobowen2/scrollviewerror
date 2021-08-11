<template>
  <view class="index">
    <text @tap="tap">{{ msg }}</text>
    <video
      v-show="src"
      id="v"
      ref="v"
      :src="src"
      :controls="false"
      :show-progress="false"
      :show-fullscreen-btn="false"
      :show-play-btn="false"
      :show-center-play-btn="false"
    />
  </view>
</template>

<script>
import './index.less'
import Comp from '../../components/comp'

const src = `http://vxcx.weishi.qq.com/vxcx.weishi.qq.com/gzc_8165_1047_0bc3p4aboaaaiaag3i6sizqbo7yec57qaf2a.f70.mp4?dis_k=7ce2360b3780a9bdca1979f624616907&dis_t=1626854911&fromtag=0&personid=1596214208417689&pver=8.25.0&wsadapt=1596214208417689_0721160831__160236443_0_0_0_27_27_0_0_0_0_0&qua=V1_WXA_WS_3.0.0_001_IDC_NEW`
const src2 = `http://vxcx.weishi.qq.com/vxcx.weishi.qq.com/gzc_9636_1047_0bc3qeabuaaakyap5hotjnqbpaiedkaqagsa.f70.mp4?dis_k=5a902b2fa1a3536c71305f59d546c646&dis_t=1626854911&fromtag=0&personid=1596214208417689&pver=8.26.0&wsadapt=1596214208417689_0721160831__160236443_0_0_0_27_27_0_0_0_0_0&qua=V1_WXA_WS_3.0.0_001_IDC_NEW`
global.src1 = src
global.src2 = src2

export default {
  components: {
  },
  data () {
    return {
      msg: 'Hello world!',
      text: 'ssssssssssssssssssssssss',
      src,
    }
  },
  mounted() {
    global.c = this
    this.ctx = wx.createVideoContext('v')
  },
  methods: {
    play() {
      this.ctx.play()
    },
    pause() {
      this.ctx.pause()
    },
    tap() {
      toggle();
    }
  }
}
let flag = true;
global.toggle = () => {
  c.play();
  setTimeout(() => { c.src='' }, 1000);
  setTimeout(() => { c.pause() }, 1200);
  setTimeout(() => {
    c.src= flag ? src2 : src1
    flag = !flag
  }, 2200);
}

</script>
