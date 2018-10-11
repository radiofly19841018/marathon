<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
/* globals wx:false */
export default {
  name: 'App',
  methods: {
    changeTitle (name) {
      var i = document.createElement('iframe')
      i.style.display = 'none'
      i.onload = function () {
        setTimeout(function () {
          i.remove()
        }, 9)
      }
      document.title = name
      document.body.appendChild(i)
    },
    wxConfig () {
      let url = 'http://wx.gc121.com/index.php?g=Api&m=Weixin&a=getJsApiSignBundle'
      let href = window.location.href
      this.$http.get(url, {
        params: {
          'token': 'weistreet',
          'url': href
        }
      }).then((data) => {
        if (data.status === 'success') {
          wx.config({
            debug: false,
            appId: data.data.appId,
            timestamp: data.data.timestamp,
            nonceStr: data.data.nonceStr,
            signature: data.data.signature,
            jsApiList: [
              'onMenuShareTimeline',
              'onMenuShareAppMessage',
              'getLocation',
              'openLocation'
            ]
          })
          // wx.ready(function() {
          //   //自定义分享内容
          //   wx.onMenuShareTimeline({
          //     title: shareDes, // 分享标题
          //     link: shareLink, // 分享链接
          //     imgUrl: shareLogoUrl, // 分享图标
          //     success: (res) => {
          //     },
          //     cancel: (res) => {
          //     }
          //   })
          //   wx.onMenuShareAppMessage({
          //     title: shareTitle,
          //     desc: shareDes,
          //     link: shareLink,
          //     imgUrl: shareLogoUrl,
          //     success: (res) => {},
          //     cancel: (res) => {}
          //   })
          // })
        }
      })
    }
  },
  created () {
    this.$root.$on('changeTitle', this.changeTitle)
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
html,body,#app{
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}
body{
  /* background-image: url('./assets/body-bg.png');
  background-position: top left;
  background-size: cover;
  background-repeat: no-repeat; */
}
</style>
