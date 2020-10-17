<template>
  <div class="chat">
    <h1 class="user">用户：{{currentUser.username}}</h1>
  </div>
</template>

<script>
  export default {
    props: ['currentUser']
  }
</script>

<style scoped>
  .chat{
    width: 500px;
    height: 700px;
    border: 1px solid #ccc;
  }
</style>
