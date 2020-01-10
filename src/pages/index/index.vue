<template>
  <div class="container">

      <div class="swiper-tab">
        <div :class="['swiper-tab-item', currentTab==0?'active':'']" data-current="0" @click="clickTab">做什么</div>
        <div :class="['swiper-tab-item', currentTab==1?'active':'']" data-current="1" @click="clickTab">推荐站点</div>
        <div :class="['swiper-tab-item', currentTab==2?'active':'']" data-current="2" @click="clickTab">作者</div>
      </div>

      <div :class = "currentTab == 0 ? 'show':'hidden'" >

        <label>暂无内容1</label>

      </div>
      <div :class = "currentTab == 1 ? 'show':'hidden'" >

        <label>暂无内容2</label>

      </div>
      <div :class = "currentTab == 2 ? 'show':'hidden'">

        <label>暂无内容3</label>

      </div>
    <!-- 路由跳转 -->
    <a @click="gotoGame('pages/counter/main')" class="counter">去往Vuex页面</a>
    <a @click="gotoGame('pages/logs/main')" class="counter">去往logs页面</a>
  </div>
</template>

<script>
// 组件引用
import card from '@/components/card'

export default {
  data () {
    return {
      motto: 'Hello World',
      currentTab: 0
    }
  },
  components: {
    card
  },
  methods: {
    gotoGame (path) {
      this.reLaunchPageTo(this.router + path)
    },
    //点击切换
    clickTab (e) {
      console.log("name",e)
      var that = this;
      if (that.currentTab === e.target.dataset.current) {
        return false;
      } else {
        that.currentTab = e.target.dataset.current
      }
    }
  }
}
</script>

<style lang="less" scoped>

.about_page{
  margin: 0 10px;
}
.swiper-tab{
    width: 100%;
    text-align: center;
    height: 88rpx;
    line-height: 88rpx;
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    color: #ccc;
    font-size: 16px;
}
.swiper-tab-item{
    width: 30%; 
    color:#434343;
}
.active{
    color:#F65959;
    /* border-bottom: 4rpx solid #F65959; */
    font-size: 16px;
    font-weight: bold;
}
.juzhong{
  margin: 0 auto;
}
.domain{
  background-color: #fff;
  height: 100%;
  margin:0 10px;
}
.show{
  display: block;
}
.hidden{
  display: none;
}

</style>
