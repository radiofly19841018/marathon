<style scoped>
  #page-index{
    position: relative;
    height: 100%;
    width: 100%;
    background-color: #5aafd6;
    background-image: url('../assets/index-bg.jpg');
    background-position: bottom left;
    background-size: 100% auto;
    background-repeat: no-repeat;
  }
  .top-info{
    padding-top: 12%;
  }
  .top-info-img{
    display: block;
    margin: 0 auto;
  }
  .info-img-1{
    margin-bottom: 20px;
    width: 74%;
  }
  .info-img-2{
    width: 75%;
  }
  .bottom-btn-box{
    position: absolute;
    bottom: 10%;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    width: 50%;
    height:50px;
    line-height: 50px;
    background:#d3007f;
    border-radius:25px;
    font-family:PingFangSC-Regular;
    font-size:18px;
    color:#ffffff;
    letter-spacing:0;
    text-align: center;
    font-weight: 200;
    z-index: 10;
  }
  .page-note{
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.79);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 100;
  }
  .note-inner{
    width: 70%;
  }
  .note-info{
    padding-top: 35px;
    background:#ffffff;
    border-radius:8px;
    overflow: hidden;
  }
  .note-title{
    margin: 0 10% 25px;
    background-color: #333333;
    height: 1px;
    text-align: center;
  }
  .note-title-text{
    position: relative;
    top: -12px;
    padding: 0 0.7em;
    font-family:PingFangSC-Medium;
    font-size:18px;
    color:#333333;
    background: #ffffff;
  }
  .note-detail{
    padding: 0 15px;
    font-family:PingFangSC-Light;
    font-size:16px;
    color:#333333;
  }
  .note-img{
    display: block;
    margin: 0;
    padding: 0;
    width: 100%;
  }
  .note-btn{
    margin: 45px auto 0;
    width: 70%;
    background-color:#dddddd;
    border-radius:25px;
    height:50px;
    line-height: 50px;
    color: #ffffff;
    text-align: center;
    font-family:PingFangSC-Regular;
    font-size:18px;
    font-weight: 100;
  }
  .note-btn.active{
    background-color:#d3007f;
  }
  .note-time{
    margin-right: 1em;
  }
</style>

<template>
  <div id="page-index">
    <div class="top-info">
      <img class="top-info-img info-img-1" src="../assets/index-logo.png" alt="">
    </div>
    <div class="bottom-btn-box" @click="showNotePage">
      我要报名
    </div>
    <div class="page-note" v-show="showNote">
      <div class="note-inner">
        <div class="note-info">
          <div class="note-title"><span class="note-title-text">活动须知</span></div>
          <div class="note-detail">1、请确认填写联系方式正确，报名成功后将发送确认短信并电话联系通知，注意查收；</div>
          <div class="note-detail">2、活动当天应穿柔软舒适的便鞋/运动鞋，以及舒适的运动/休闲服装；</div>
          <div class="note-detail">3、活动中需听从工作人员安排集合、分队、游览项目，由擅自离队发生的所有意外情况【惠氏制药有限公司】概不负责；</div>
          <div class="note-detail">4、本次活动最终解释权归【惠氏制药有限公司】所有。</div>
          <img class="note-img" src="../assets/note-bg.png" alt="">
        </div>
        <div class="note-btn" :class="{active: nextPage}">
          <span class="note-time" v-show="countdown !== 0">{{countdown}}S</span><span @click="goNextPage">确认</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* globals wx:false */
export default {
  name: 'index',
  data () {
    return {
      countdown: 10,
      showNote: false,
      nextPage: false
    }
  },
  methods: {
    showNotePage () {
      this.showNote = true
      this.startCountdown()
    },
    startCountdown () {
      if (this.countdown > 0) {
        this.countdown--
        setTimeout(() => {
          this.startCountdown()
        }, 1000)
      } else {
        this.nextPage = true
      }
    },
    goNextPage () {
      if (this.nextPage) {
        this.$router.push({
          name: 'detail'
        })
      }
    },
    wxConfig () {
      let url = 'http://wx.gc121.com/index.php?g=Api&m=Weixin&a=getJsApiSignBundle'
      let shareTitle = '行动力，游城市 | 钙尔奇邀您一起成为“行动力达人”'
      let shareLink = 'http://sites.gc121.com/xdl/admin/index.php?g=Api&m=Index&a=index'
      let shareDes = '描述：点击免费报名参加'
      let shareLogoUrl = 'http://sites.gc121.com/xdl/view/src/assets/share_logo.png'
      let href = window.location.href
      this.$http.get(url, {
        params: {
          'token': 'weistreet',
          'url': href
        }
      }).then((res) => {
        if (res.data.status === 'success') {
          console.log(res.data.data.signature)
          wx.config({
            debug: false,
            appId: res.data.data.appId,
            timestamp: res.data.data.timestamp,
            nonceStr: res.data.data.nonceStr,
            signature: res.data.data.signature,
            jsApiList: [
              'onMenuShareTimeline',
              'onMenuShareAppMessage',
              'getLocation',
              'openLocation'
            ]
          })
          wx.ready(function () {
            wx.onMenuShareTimeline({
              title: shareDes,
              link: shareLink,
              imgUrl: shareLogoUrl
            })
            wx.onMenuShareAppMessage({
              title: shareTitle,
              desc: shareDes,
              link: shareLink,
              imgUrl: shareLogoUrl
            })
          })
        }
      })
    }
  },
  beforeRouteEnter (to, from, next) {
    next(vm => {
      vm.wxConfig()
      vm.$root.$emit('changeTitle', '行动力 游城市')
      if (window.location.href.indexOf('userType=0') !== -1) {
        vm.$router.replace({
          name: 'detail',
          query: {
            userType: 0
          }
        })
      }
    })
  }
}
</script>
