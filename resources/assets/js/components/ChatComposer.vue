<template>


    <div class="chat-composer">

      <input id="message" type="text"  placeholder="Enter your msg here...." v-model="messageText" v-on:keydown.enter="sendMessage">

      <button   class="btn btn-primary" @click="sendMessage">Send</button>

    </div>
</template>

<script>
export default{
data() {

  return {
    messageText: ''
    }
  },

  methods: {

    sendMessage() {
      /*console.log(this.messageText);*/
      this.$emit('messagesent', {
        message: this.messageText,
        user:  {
          name: $('.navbar-right .dropdown-toggle').text()
        }
      });
      this.messageText="";
    }

  }
}



</script>

<style>
.chat-composer{
  display: flex;
}
.chat-composer input {
    flex: 1 auto;
    padding: .5rem 1rem;
    margin-top: 2em;
}

.chat-composer button {
    border-radius: 5;
    margin-top: 2em;
}

</style>
