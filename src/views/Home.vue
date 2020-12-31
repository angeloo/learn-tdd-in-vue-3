<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <new-message-form @send="addMessages" />
    <messages-list :messages="messages" />
    {{ messages }}
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import NewMessageForm from '@/components/NewMessageForm.vue'; // @ is an alias to /src
import MessagesList from '@/components/MessagesList.vue';

@Options({
  components: {
    NewMessageForm,
    MessagesList
  },
  data() {
    return {
      messages: []
    }
  },
  methods: {
    addMessages(text: string) {
      this.messages.unshift(text);
    }
  },
})
export default class Home extends Vue {}
</script>
