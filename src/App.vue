<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello fmsg="msg from father" v-on:child-tell-me-something="listenToMyBoy"></hello>
    <p>child tells me : {{childWords}}</p>
  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  data () {
    return {
      childWords: ''
    }
  },
  components: {
    Hello
  },
  methods: {
    listenToMyBoy: function (msg) {
      this.childWords = msg
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
