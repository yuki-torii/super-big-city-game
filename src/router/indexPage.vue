<template>
  <div class="indexPage">
    <div v-if="stage === 0">
      <div>这是一片空地，你将建立起自己的城市</div>
      <el-button @click="stage = 1">嗯，好的</el-button>
    </div>
    <div v-if="stage === 1">
      <el-row>
        <el-col :span="8">
          <p class="tips">你现在需要收集木材升起篝火 🔥</p>
          <p>统计</p>
          <el-button>人口 {{ people }}</el-button>
          <el-button>木材 {{ wood }}</el-button>
          <p>包裹</p>
          <el-button v-for="item in bag">
            {{ item.name }}
          </el-button>
        </el-col>
        <el-col :span="8">
          <p>采集</p>
          <el-button @click="wood++">收集木材</el-button>
          <p>生产</p>
          <el-button @click="bag.push({ name: '篝火' }); wood -= 10">篝火</el-button>
          <p>建造</p>
          <el-button>帐篷</el-button>
        </el-col>
        <el-col :span="8"><div class="">3</div></el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'indexPage',
  data () {
    return {
      people: 1,
      time: 0,
      wood: 0,
      stage: 0,
      bag: []
    }
  },
  watch: {
  },
  mounted () {
    const self = this
    console.log(self)
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
