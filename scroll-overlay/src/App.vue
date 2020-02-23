<style>
.overlay {
  border: 1px solid #CCC;
  border-radius: 4px;
  height: 300px;
  width: 300px;
}
.item {
  height: 50px;
  line-height: 50px;
  border-radius: 2px;
  margin: 4px;
  padding: 0 10px;
  background-color: #EEEEEE;
  color: #333;
}
</style>

<template>
  <div>
    <overlay-scrollbars ref="scrollbars" class="overlay">
      <div
        class="item"
        v-for="n in count"
        :key="n"
        :ref="`item-${n}`"
        @click="click(n)">
        index: {{ n }}
      </div>
    </overlay-scrollbars>
    <button @click="add">ADD ONE</button>
    <button @click="goto">GO TO</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      count: 10
    }
  },
  methods: {
    add () {
      this.count ++
    },
    click (index) {
      const instance = this.$refs.scrollbars.osInstance()
      instance.scroll({
        el: this.$refs[`item-${index}`][0],
        margin: true
      }, 300)
    },
    goto () {
      const instance = this.$refs.scrollbars.osInstance()
      const height = instance.getState().contentScrollSize.height
      instance.scroll({
        x: 0,
        y: Math.round(Math.random() * height) + 'px'
      }, 300)
    }
  }
}
</script>
