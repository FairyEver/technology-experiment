<style>
.overlay {
  border: 1px solid #CCC;
  border-radius: 4px;
  min-height: 200px;
  min-width: 200px;
  max-height: 600px;
  max-width: 600px;
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
    <overlay-scrollbars
      ref="scrollbars"
      class="overlay"
      :options="{ scrollbars: { autoHide: 'scroll' }, resize: 'both' }">
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
