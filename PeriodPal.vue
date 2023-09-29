<template>
    <div class="chat-container">
      <h1>Simple Chatbot</h1>
      <div id="chat">
        <slot></slot>
      </div>
      <form id="user-input" @submit.prevent="sendMessage">
        <input type="text" id="message" v-model="userMessage" placeholder="Type your response...">
        <button type="submit">Send</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        userMessage: '',
      };
    },
    methods: {
      sendMessage() {
        // Handle the user's message here (you can emit an event or call a method to handle it)
        // For this example, let's emit an event with the user's message
        this.$emit('user-message', this.userMessage);
        // Clear the input field
        this.userMessage = '';
      },
    },
  };
  </script>
  