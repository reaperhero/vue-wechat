<template>
  <div id="app">
    <div class="content">
      <chatcom :currentUser="currentUser"></chatcom>
      <userlistcom @chooseuser='toggleUser' :userlist="userlist"></userlistcom>
    </div>
  </div>
</template>

<script>
  import chatcom from "./components/chatcom";
  import userlistcom from "./components/userlistcom";

  export default {
    name: 'App',
    components: {
      chatcom,
      userlistcom,
    },
    data() {
      return {
        msg: '聊天',
        userlist: [
          {
            username: "小明",
            headerimg: require('./assets/img/1.jpeg')
          },
          {
            username: "小黑",
            headerimg: require('./assets/img/2.jpeg')
          },
          {
            username: "小红",
            headerimg: require('./assets/img/3.jpg')
          },
          {
            username: "小白",
            headerimg: require('./assets/img/4.jpeg')
          }
        ],
        currentUser:{
          username:"小明",
          headerimg:require('./assets/img/1.jpeg')
        }
      }
    },
    methods: {
      toggleUser:function(index) {
        this.currentUser = this.userlist[index]
      }
    }
  }
</script>

<style scoped>
  .content {
    display: flex;
    width: 800px;
    height: 700px;
    margin: 100px auto;
  }
</style>
