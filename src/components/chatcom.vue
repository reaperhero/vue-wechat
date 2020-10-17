<template>
  <div class="chat">
    <h1 class="user">用户：{{currentUser.username}}</h1>
    <div class="chatlist">
      <chatitem v-for="(item,index) in chatList" :chatItem='item' :key='index'>
        {{item.chatcontent}}
      </chatitem>
    </div>
    <chatinputcom :sendEvent='sendEvent'></chatinputcom>
  </div>
</template>

<script>
  import chatinputcom from "./chatinputcom";
  import chatitem from "./chatItem";

  export default {
    props: ['currentUser'],
    data() {
      return {
        chatList: [
          {
            user: {
              username: '小米',
              headerimg: require('../assets/img/1.jpeg')
            },
            chatcontent: '吃了么?'
          }
        ]
      }
    },
    components: {
      chatinputcom,
      chatitem
    },
    methods: {
      sendEvent: function (value) {
        this.chatList.push({
          user: {
            username: '小明',
            headerimg: require('../assets/img/1.jpeg')
          },
          chatcontent: value
        })
        console.log(this)
        this.chatList.push({
          user: this.$root.$children[0].currentUser,
          chatcontent: new Date()
        })
      }
    },
  }
</script>

<style scoped>
  .chat {
    width: 500px;
    height: 700px;
    border: 1px solid #ccc;
  }
</style>
