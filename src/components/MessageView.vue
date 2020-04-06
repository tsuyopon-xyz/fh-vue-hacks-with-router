<template>
  <div>
    <TextBox :onPost="addMessage"/>
    <div class="devider"></div>
    <MessageList :messages="reversedMessages" />
  </div>
</template>

<script>
import TextBox from './TextBox';
import MessageList from './MessageList';

export default {
  components: {
    TextBox,
    MessageList
  },
  data() {
    return {
      messages: []
    };
  },
  computed: {
    reversedMessages() {
      return this.messages.slice().reverse();
    }
  },
  methods: {
    addMessage(message) {
      this.messages.push(message);
    }
  }
}
</script>

<style scoped>
.devider {
  border-top: 10px solid #ccc;
}
</style>