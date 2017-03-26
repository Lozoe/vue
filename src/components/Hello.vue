<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" v-model="newItem" v-on:keyup.enter="addNew">
    <ul>
      <li v-for="item in items" v-bind:class="{finished: item.isFinished}" v-on:click="toggleFinished(item)">
          {{item.label}}
      </li>
    </ul>
    <div>{{fmsg}}</div>
    <button @click="onClickMe">click me</button>
    <button @click="onClickOpenMouse">open mouse</button>
  </div>
</template>

<script>
import Store from '../store'
console.log(Store)
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      items: Store.fetch(),
      newItem: ''
    }
  },
  watch: {
    items: {
      handler: function (val, oldVal) {
        Store.save(val)
      },
      deep: true
    }
  },
  props: ['fmsg'],
  methods: {
    toggleFinished: function (item) {
      item.isFinished = !item.isFinished
    },
    addNew: function () {
      this.items.push({
        label: this.newItem,
        isFinished: false
      })
      this.newItem = ''
    },
    onClickMe: function () {
      console.log(this.fmsg)
    },
    onClickOpenMouse: function () {
      this.$emit('child-tell-me-something', this.msg)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  /*list-style-type: none;*/
  padding: 0;
}

li {
  /*display: inline-block;*/
  margin: 0 10px;
}

a {
  color: #42b983;
}
.finished {
    text-decoration: underline;
    color: green;
}
</style>
