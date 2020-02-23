<style lang="scss">
.scroll {
  position: relative;
  width: 600px;
  height: 400px;
  border: 1px solid #CCC;
  overflow: hidden;
  .item {
    height: 30px;
    border-bottom: 1px solid #CCC;
    line-height: 30px;
  }
}
</style>

<template>
  <div>
    <div ref="scroll" class="scroll">
      <div v-for="n in 100" :key="n" class="item">n</div>
    </div>
  </div>
</template>

<script>
import PerfectScrollbar from 'perfect-scrollbar'
import 'perfect-scrollbar/css/perfect-scrollbar.css'
export default {
  name: 'scroll',
  data () {
    return {
      ps: null
    }
  },
  mounted () {
    this.ps = new PerfectScrollbar(this.$refs.scroll, {
      swipeEasing: false,
      wheelPropagation: false
    })
  }
}
</script>
