<template>
  <view class="container" @tap="change">
    <scroll-view class="scroll" :scroll-y="true" :enhanced="true" :paging-enabled="true" :show-scrollbar="true" :scroll-with-animation="true" :scroll-into-view="jumpItem">
      <view v-for="item in list" :key="item" class="item" :style="{ top: item * 100 + '%' }">
        <video
          class="video"
          :src="src"
        />
        <view class="mask">{{Array(100).fill(item).join()}}</view>
      </view>
    </scroll-view>
  </view>
</template>

<script>

export default {
  components: {
  },
  data () {
    return {
      jumpItem: null,
      list: [0,1,2,3,4],
      src: 'http://q.weishi.qq.com/q.weishi.qq.com/szg_4521_50001_0bf2yeabaaaa2uaakjio3rqvdqodcdaqaeca.f60.mp4?dis_k=f3046bc61fe332a17a83857b9c7d0a2d&dis_t=1628665124&fromtag=0&personid=1596214208417689&pver=1.1.0&source=50001&wsadapt=1596214208417689_0811145844__160251826_0_0_0_2_25_0_0_0_0_0&qua=V1_WXA_WS_3.0.0_001_IDC_NEW'
    }
  },
  methods: {
    change() {
      this.list = [1,2,3,4]
    }
  }
}

</script>

<style>
Page{
  width: 100%;
  height: 100vh;
}
.container{
  height: 100%;
}
.scroll{
  width: 100%;
  height: 100%;
  position: relative;
}
.item{
  width: 100%;
  height: 100%;
  overflow: hidden;
  position: absolute;
  left: 0;
}
.video{
  width: 100%;
  height: 100%;
}
.mask{
  position: absolute;
  left: 0;
  top: 100rpx;
  color: red;
  font-weight: bold;
}
</style>
