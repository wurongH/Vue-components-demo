<template>
  <div class="son">
    <h1>这是子组件</h1>
    <div>这是父组件传递给子组件的值：{{msg}}</div>
    <div @click="changeTitle" style="cursor:pointer">{{title}}</div>
    <el-input v-model="data" placeholder="这是子组件" size="small" style="width: 200px"/>
  </div>
</template>

<script>
export default {
  props: {
    msg: String
  },
  data() {
    return {
      title: '子组件的标题',
      data: ''
    }
  },
  watch: {
    data(val) {
      if (val) {
        this.$emit('titleChanged', this.data)
      } else {
        this.$emit('titleChanged', '')
      }
    }
  },
  methods: {
    changeTitle() {
      // this.$emit('titleChanged', this.data)
    }
  },

}
</script>


<style scoped>
.son {
  color: skyblue
}
.son > h1{
  color: skyblue
}
</style>
