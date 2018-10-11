<style scoped>
  #page-detail{
    padding-top: 40px;
    padding-bottom: 20px;
    min-height: 100%;
    width: 100%;
    background-image: url('../assets/body-bg.png');
    background-position: top left;
    background-size: 100% auto;
    background-repeat: no-repeat;
  }
  .top-info-img{
    display: block;
    margin: 0 auto 20px;
  }
  .info-img-2{
    margin-bottom: 20px;
    width: 75%;
  }
  .page-form{
    padding: 0 20px;
  }
  .form-row{
    width: 100%;
    margin-bottom: 20px;
    display: flex;
    justify-content: stretch;
    align-items: center;
    font-family:PingFangSC-Regular;
    font-size:16px;
    color:#333333;
  }
  .form-row-name{
    padding-right: 10px;
  }
  .form-row-name-inner{
    width: 5em;
    display: inline-flex;
    justify-content: space-between;
  }
  .input-box{
    position: relative;
    flex-grow: 1;
    display: flex;
    min-height: 40px;
    align-items: center;
  }
  .form-input{
    position: relative;
    flex-grow: 1;
    border:1px solid #bdbdbd;
    border-radius:7px;
    height:38px;
    line-height: 38px;
    background-color: transparent;
    outline: none;
    text-indent: 1em;
    font-family:PingFangSC-Regular;
    font-size:14px;
    color:#333333;
  }
  .form-input:focus{
    outline: none;
  }
  .form-input::-webkit-input-placeholder{
      font-family:PingFangSC-Regular;
      font-size:14px;
      color:#c2c2c2;
  }
  .form-input::-moz-placeholder{
      font-family:PingFangSC-Regular;
      font-size:14px;
      color:#c2c2c2;
  }
  .form-input:-moz-placeholder{
      font-family:PingFangSC-Regular;
      font-size:14px;
      color:#c2c2c2;
  }
  .form-input:-ms-input-placeholder{
      font-family:PingFangSC-Regular;
      font-size:14px;
      color:#c2c2c2;
  }
  .chick-box{
    margin-right: 6px;
    position: relative;
    display: inline-flex;
    justify-content: center;
    align-items: center;
    height: 15px;
    width: 15px;
    border-radius: 50%;
    border: 1px solid #d3007f;
    background-color: transparent;
  }
  .chick-box.active{
    background-color: #d3007f;
  }
  .icon-right{
    position: relative;
    top: -1px;
    display: block;
    height: 5px;
    width: 8px;
    border-left: 1px solid transparent;
    border-bottom: 1px solid transparent;
    transform: rotate(-45deg);
  }
  .icon-right-text{
    width: 6em;
  }
  .active .icon-right{
    border-left: 1px solid #ffffff;
    border-bottom: 1px solid #ffffff;
  }
  .form-input-list{
    position: absolute;
    left: 0;
    right: 0;
    top: 100%;
    margin-top: 10px;
    border:1px solid #bdbdbd;
    border-radius:7px;
    line-height: 38px;
    max-height: 190px;
    overflow-y: scroll;
    overflow-x: hidden;
    background-color: #ffffff;
    outline: none;
    text-indent: 1em;
    font-family:PingFangSC-Regular;
    font-size:14px;
    color:#333333;
    z-index: 99;
  }
  .form-input-address{
    margin-right: 20px;
  }
  .add-partner{
    padding-top: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family:PingFangSC-Regular;
    font-size:14px;
    color:#373737;
  }
  .icon-cir{
    display: inline-block;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    text-align: center;
    line-height: 16px;
    border: 1px solid #373737;
  }
  .icon-p-right{
    margin-right: 16px;
  }
  .page-sub-box{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .control-btn{
    flex-grow: 1;
    margin: 20px 20px 0;
    background:#d3007f;
    border-radius:25px;
    height:50px;
    line-height: 50px;
    text-align: center;
    font-family:PingFangSC-Regular;
    font-size:18px;
    color:#ffffff;
  }
  .partner-list{
    padding: 0 20px;
    margin-bottom: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .partner-list-inner{
    margin-right: 16px;
    display: inline-block;
    font-family:PingFangSC-Regular;
    font-size:14px;
    color:#333333;
    border:1px solid #bdbdbd;
    border-radius:7px;
    height: 38px;
    line-height:38px;
    text-align: center;
    overflow: hidden;
    text-overflow:ellipsis;
    white-space: nowrap;
  }
  .list-inner-name{
    width: 5em;
  }
  .list-inner-phone{
    width: 9em;
  }
  .list-inner-sex{
    width: 3em;
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
    padding: 30px 0 0;
    width: 70%;
    background:#ffffff;
    border-radius:8px;
    overflow: hidden;
  }
  .note-btn{
    margin: 45px auto 10px;
    width: 8em;
    background:#d3007f;
    border-radius:25px;
    height:40px;
    line-height: 40px;
    color: #ffffff;
    text-align: center;
    font-family:PingFangSC-Regular;
    font-size:18px;
    color:#ffffff;
    font-weight: 100;
  }
  .note-inner-text{
    margin-top: 20px;
    font-family:PingFangSC-Regular;
    font-size:18px;
    color:#333333;
    text-align: center;
  }
  .note-inner-img{
    display: block;
    margin: 0;
    padding: 0;
  }
  .note-img-1{
    width: 26%;
    margin: 0 auto;
  }
  .note-img-2{
    width: 100%;
  }
  .icon-down{
    position: absolute;
    right: 12px;
    top: 35%;
    width: 8px;
    height: 8px;
    border-left: 1px solid #bbbbbb;
    border-bottom: 1px solid #bbbbbb;
    transform: rotate(-45deg);
  }
</style>

<template>
  <div id="page-detail">
    <img class="top-info-img info-img-2" src="../assets/index-title.png" alt="">
    <form class="page-form" action="">
      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>姓</span>
            <span>名</span>
          </div>:
        </div>
        <div class="input-box">
          <input class="form-input" type="text" placeholder="请填写您的姓名" v-model="listName" maxlength="7">
        </div>
      </div>

      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>姓</span>
            <span>别</span>
          </div>:
        </div>
        <div class="input-box">
          <span class="chick-box" :class="{active: listSex === 0}" @click="listSex = 0"><span class="icon-right"></span></span><span class="icon-right-text">女</span>
          <span class="chick-box" :class="{active: listSex === 1}" @click="listSex = 1"><span class="icon-right"></span></span><span>男</span>
        </div>
      </div>

      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>年</span>
            <span>龄</span>
          </div>:
        </div>
        <div class="input-box">
          <div class="form-input" @click="checkShowList(1)">
            {{listAge | formatAge}}
            <div class="icon-down"></div>
            <div class="form-input-list" v-show="showList === 1">
              <div class="list-row" @click.stop="checkAge(1)">
                40岁以下
              </div>
              <div class="list-row" @click.stop="checkAge(2)">
                40-55岁
              </div>
              <div class="list-row" @click.stop="checkAge(3)">
                55-65岁
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>手</span>
            <span>机</span>
            <span>号</span>
            <span>码</span>
          </div>:
        </div>
        <div class="input-box">
          <input class="form-input" type="text" placeholder="请填写您的手机号码" v-model="listTel" maxlength="18">
        </div>
      </div>

      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>有</span>
            <span>无</span>
            <span>疾</span>
            <span>病</span>
          </div>:
        </div>
        <div class="input-box">
          <span class="chick-box" :class="{active : listIsIll === 0}" @click="listIsIll = 0"><span class="icon-right"></span></span><span class="icon-right-text">无疾病</span>
          <span class="chick-box" :class="{active : listIsIll === 1}" @click="listIsIll = 1"><span class="icon-right"></span></span><span>有疾病</span>
        </div>
      </div>

      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>地</span>
            <span>址</span>
          </div>:
        </div>
        <div class="input-box">
          <div class="form-input form-input-address" @click="checkShowList(2)">
            {{listTown | formatPosition}}
            <div class="icon-down"></div>
            <div class="form-input-list" v-show="showList === 2">
              <div class="list-row" v-for="(city, index) of cityList" :key="'town' + index" @click.stop="checkTown(city.town)">
                {{city.town}}
              </div>
            </div>
          </div>
          <div class="form-input" @click="checkShowList(3)">
            {{listStreet | formatPosition}}
            <div class="icon-down"></div>
            <div class="form-input-list" v-show="showList === 3" v-for="(city, index) of cityList" :key="'street' + index" v-if="city.town === listTown">
              <div class="list-row" v-for="street of city.street" :key="street" @click.stop="checkStreet(street)">
                {{street}}
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="form-row">
        <div class="form-row-name">
          <div class="form-row-name-inner">
            <span>集</span>
            <span>合</span>
            <span>地</span>
            <span>点</span>
          </div>:
        </div>
        <div class="input-box">
          <div class="form-input" @click="checkShowList(4)">
            {{listPosition | formatPosition}}
            <div class="icon-down"></div>
            <div class="form-input-list" v-show="showList === 4">
              <div class="list-row" v-for="position of positionList" :key="position" @click.stop="checkPosition(position)">
                {{position}}
              </div>
            </div>
          </div>
        </div>
      </div>
    </form>

    <div class="partner-list" v-for="(user, index) of userData" :key="'user' + index" v-show="pageType === 1">
      <div>
        <span class="partner-list-inner list-inner-name">{{user.trueName}}</span>
        <span class="partner-list-inner list-inner-phone">{{user.tel}}</span>
        <span class="partner-list-inner list-inner-sex">{{user.sex | formatSex}}</span>
      </div>
      <span class="icon-cir" @click="delUser(index)">&#45;</span>
    </div>

    <div class="add-partner" v-show="pageType === 1" @click="toAddUser">
      <span class="icon-cir icon-p-right">&#43;</span>添加同行人员
    </div>
    <div class="page-sub-box">
      <div class="control-btn submit-btn" v-show="pageType === 1" @click="pageSubmit">
        提交
      </div>
      <div class="control-btn cancel-btn" v-show="pageType === 0" @click="addCancel">
        取消
      </div>
      <div class="control-btn add-btn" v-show="pageType === 0" @click="addSubmit">
        增加
      </div>
    </div>
    <div class="page-note" v-show="success">
      <div class="note-inner">
        <img class="note-inner-img note-img-1" src="../assets/success.png" alt="">
        <div class="note-inner-text">
          恭喜您，报名成功！
        </div>
        <div class="note-btn">
          <span @click="success = false">确&nbsp;&nbsp;认</span>
        </div>
        <img class="note-inner-img note-img-2" src="../assets/note-bg.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'detail',
  data () {
    return {
      clickEvn: false,
      success: false,
      pageType: 1,
      cityList: require('../assets/address.json'),
      showList: 0,
      listName: '',
      listSex: 0,
      listTel: '',
      listIsIll: 0,
      listTown: '',
      listStreet: '',
      listPosition: '',
      listAge: 1,
      myData: {
        trueName: '',
        sex: 0, // 1男 0女
        tel: '',
        isIll: 0, // 是否生病 1是 0否
        town: '',
        street: '',
        position: '',
        age: 1 // 1:40岁以下，2:40-55岁，3:55-65岁
      },
      userData: [],
      positionList: [
        '111',
        '222',
        '333'
      ]
    }
  },
  watch: {
    listTown (newVal, oldVal) {
      if (this.clickEvn && oldVal !== newVal) {
        this.listStreet = ''
        this.listPosition = ''
        this.clickEvn = false
      }
    },
    listStreet (newVal, oldVal) {
      if (this.clickEvn && oldVal !== newVal) {
        this.listPosition = ''
        this.clickEvn = false
      }
    }
  },
  methods: {
    checkAge (val) {
      this.listAge = val
      this.showList = 0
    },
    checkShowList (value) {
      if (this.showList === value) {
        this.showList = 0
      } else {
        this.showList = value
      }
    },
    checkTown (town) {
      this.clickEvn = true
      this.listTown = town
      this.showList = 3
    },
    checkStreet (street) {
      this.clickEvn = true
      this.listStreet = street
      this.showList = 4
    },
    checkPosition (position) {
      this.listPosition = position
      this.showList = 0
    },
    resetData () {
      this.showList = 0
      this.listName = ''
      this.listSex = 0
      this.listTel = ''
      this.listIsIll = 0
      this.listTown = ''
      this.listStreet = ''
      this.listPosition = ''
      this.listAge = 1
    },
    saveMyData () {
      this.myData.trueName = this.listName
      this.myData.sex = this.listSex
      this.myData.tel = this.listTel
      this.myData.isIll = this.listIsIll
      this.myData.town = this.listTown
      this.myData.street = this.listStreet
      this.myData.position = this.listPosition
      this.myData.age = this.listAge
    },
    recoveryMyData () {
      this.listName = this.myData.trueName
      this.listSex = this.myData.sex
      this.listTel = this.myData.tel
      this.listIsIll = this.myData.isIll
      this.listTown = this.myData.town
      this.listStreet = this.myData.street
      this.listPosition = this.myData.position
      this.listAge = this.myData.age
    },
    addUserData () {
      this.listName = this.userData[this.userData.length - 1].trueName
      this.listSex = this.userData[this.userData.length - 1].sex
      this.listTel = this.userData[this.userData.length - 1].tel
      this.listIsIll = this.userData[this.userData.length - 1].isIll
      this.listTown = this.userData[this.userData.length - 1].town
      this.listStreet = this.userData[this.userData.length - 1].street
      this.listPosition = this.userData[this.userData.length - 1].position
      this.listAge = this.userData[this.userData.length - 1].age
    },
    toAddUser () {
      this.saveMyData()
      this.pageType = 0
      if (this.userData.length > 0) {
        this.addUserData()
      } else {
        this.resetData()
      }
      this.$root.$emit('changeTitle', '随行人员信息')
    },
    addCancel () {
      this.pageType = 1
      this.recoveryMyData()
      this.$root.$emit('changeTitle', '填写信息')
    },
    addSubmit () {
      if (this.listName && this.listTel && this.listTown && this.listStreet && this.listPosition) {
        this.pageType = 1
        let _userData = {
          trueName: this.listName,
          sex: this.listSex,
          tel: this.listTel,
          isIll: this.listIsIll,
          town: this.listTown,
          street: this.listStreet,
          position: this.listPosition,
          age: this.listAge
        }
        this.userData.push(_userData)
        this.recoveryMyData()
        this.$root.$emit('changeTitle', '填写信息')
      } else {
        this.errMsg()
      }
    },
    delUser (val) {
      this.userData.splice(val, 1)
    },
    pageSubmit () {
      this.saveMyData()
      if (this.myData.trueName && this.myData.tel && this.myData.town && this.myData.street && this.myData.position) {
        this.postData()
      } else {
        this.errMsg()
      }
    },
    postData () {
      this.$http.post('http://sites.gc121.com/xdl/admin/index.php?g=Api&m=Index&a=reg', {
        myData: this.myData,
        userData: this.userData
      }).then(res => {
        if (res.data.status === 'success') {
          this.showSuccess()
        } else if (res.data.status === 'error') {
          alert(res.data.msg)
        } else if (res.data.status === 'timeout') {
          window.location.href = res.data.url
        }
      }).catch(res => {
        alert('网络繁忙')
      })
    },
    showSuccess () {
      this.success = true
    },
    errMsg () {
      alert('请填写完整信息')
    }
  },
  filters: {
    formatAge (val) {
      if (val === 2) {
        return '40-55岁'
      } else if (val === 3) {
        return '55-65岁'
      } else {
        return '40岁以下'
      }
    },
    formatSex (val) {
      if (val === 1) {
        return '男'
      } else {
        return '女'
      }
    },
    formatPosition (val) {
      if (val === '') {
        return '请选择'
      } else {
        return val
      }
    }
  },
  mounted () {
    this.$root.$emit('changeTitle', '填写信息')
  }
}
</script>
