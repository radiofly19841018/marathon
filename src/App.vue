<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
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
