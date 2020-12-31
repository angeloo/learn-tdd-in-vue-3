<template>
  <div>
    <input
      type="text"
      data-test="messageText"
      v-model="inputText"
    />
    <button
      data-test="sendButton"
      @click="send"
    >
      Send
    </button>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  data() {
      return {
          inputText: ""
      }
  },
  emits: ['send'],
  methods: {
      send() {
          this.$emit('send', this.inputText);
          this.inputText = "";
      }
  }
})

export default class NewMessageForm extends Vue {}
</script>
