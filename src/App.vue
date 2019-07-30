<template>
  <div id="app">
    <h1>这是父组件</h1>
    <div> 这里展示子组件传给父组件的值：{{title}}</div>
    <hr />
    <el-input v-model="msg" placeholder="这是父组件" size="small" style="width: 200px"/>
    <hr />
    <son
      :msg="msg"
      @titleChanged="updataTitle">
    </son>
    
  </div>
</template>

<script>
import son from './components/son'
export default {
  name: 'app',
  components: {
    son
  },
  data() {
    return {
      msg: '',
      title: ''
    }
  },
  methods: {
    updataTitle(e) {
      this.title = e
    }
  }
}
</script>

<style>

</style>
