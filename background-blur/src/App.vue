<template>
  <div id="app">
    <p>asdas</p>
    <box/>
    <p>asdas</p>
    <box/>
    <p>asdas</p>
    <box/>
    <p>asdas</p>
    <box/>
    <p>asdas</p>
    <box/>
    <p>asdas</p>
    <box/>
    <p>asdas</p>
    <box/>
    <p>asdas</p>
  </div>
</template>

<script>
import box from '@/components/box.vue'

export default {
  name: 'App',
  components: {
    box
  }
}
</script>

<style lang="scss">
html, body {
  background-color: #fff;
  height: 100%;
  margin: 0;
  padding: 0;
  #app {
    padding: 100px;
    height: 100%;
    background-image: url($backgroundImage);
    background-size: cover;
    background-attachment: fixed;
    overflow: hidden;
  }
}
</style>
