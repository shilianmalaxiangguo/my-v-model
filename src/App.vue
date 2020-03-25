<template>
  <div id="app">
    <Button @click="show = true">v-model控制组件显隐</Button>
    <my-modal v-model="show" @on-ok="handleOk" @on-close="handleClose" :msg="msg" @get-msg="getMsg"></my-modal>
    <p>show:{{show}}</p>
  </div>
</template>
<script>
import myModal from './components/my-modal'
export default {
  components:{
    myModal
  },
  data() {
    return {
      show:false,
      msg:'dongcidaci'
    }
  },
  methods:{
    handleOk() {
      console.log('i am ok!')   
    },
    handleClose() {
      console.log('i am close!')
    },
    getMsg(msg) {
      console.log('msg',msg)
    }
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
