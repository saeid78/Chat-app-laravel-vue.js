<template lang="html">
  <div class="chat-log">

    <!-- loop throuth the msg and binding with message property in chatmessage component-->
    <chat-message v-for="message in messages" :message="message"></chat-message>

    <div class="empty" v-show="messages.length === 0">
      Nothing!
    </div>
  </div>
</template>
<script>
export default {
      props: ['messages']
}
</script>

<style>
.chat-log .chat-message:nth-child(even) {
  background-color: #ccc;
}
.empty {
  padding: 1rem;
  text-align: center;
}
</style>
