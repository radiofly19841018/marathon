<template>
  <div id="app">
    <router-view/>
    <div class="page-note" v-show="errMsgShow">
      <div class="note-inner">
        <div class="note-info">
          <div class="note-title"><span class="note-title-text">提示信息</span></div>
          <div class="note-detail">{{errMsg}}</div>
          <img class="note-img" src="./assets/note-bg.png" alt="">
        </div>
        <div class="note-btn active">
          <span @click="closeMsg">确认</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      errMsg: '',
      errMsgShow: false
    }
  },
  methods: {
    showMsg (msg) {
      this.errMsg = msg
      this.errMsgShow = true
    },
    closeMsg () {
      this.errMsg = ''
      this.errMsgShow = false
    },
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
    }
  },
  created () {
    this.$root.$on('changeTitle', this.changeTitle)
    this.$root.$on('showMsg', this.showMsg)
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

<style scoped>
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
    padding: 15px;
    font-family:PingFangSC-Light;
    font-size:18px;
    color:#333333;
    text-align: center;
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
</style>
