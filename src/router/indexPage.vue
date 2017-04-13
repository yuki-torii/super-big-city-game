<template>
  <div class="indexPage">
    <h2>状态栏</h2>
    <div>第 {{ time }} 天</div>
  </div>
</template>

<script>
export default {
  name: 'indexPage',
  data () {
    return {
      time: 0,
      wood: 0,
      forest: 1000
    }
  },
  mounted () {
    const self = this
    setInterval(() => {
      self.time++
      self.forest--
    }, 1000)
  }
}
</script>

<style lang="css" scoped>
.forest {
  width: 10px;
  height: 10px;
  display: inline-block;
  background: greenyellow;
}
</style>
