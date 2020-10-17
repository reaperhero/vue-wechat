<template>
  <div class="chatItem">
    <img :style="imgStyle" :src="chatItem.user.headerimg">
    <div>
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "chatItem",
    data() {
      return {
        imgStyle: {
          width: "60px",
          height: "60px"
        }
      }
    },
    props: ['chatItem']
  }
</script>

<style scoped>
  .chatItem {
    display: flex;
  }
</style>
