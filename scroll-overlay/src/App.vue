<style>
.overlay {
  border: 1px solid #333;
  border-radius: 4px;
  height: 300px;
  width: 300px;
}
</style>

<template>
  <div>
    <overlay-scrollbars class="overlay">
      <p v-for="n in 100" :key="n">n</p>
    </overlay-scrollbars>
  </div>
</template>
