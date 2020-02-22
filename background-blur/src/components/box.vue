<style lang="scss">
.demo {
  height: 200px;
  width: 200px;
  line-height: 200px;
  text-align: center;
  font-size: 64px;

  border-radius: 4px;
  box-shadow: 0 10px 10px rgba(#000, .1);

  box-sizing: border-box;
  z-index: 1;
  @extend .blur;
}
</style>

<template>
  <div class="demo">
    Hello
  </div>
</template>

<script>
export default {
  name: 'demo'
}
</script>
