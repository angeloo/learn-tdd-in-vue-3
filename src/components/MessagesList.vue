<template>
  <ul>
    <li v-for="message in messages" :key="message">
      {{ message }}
    </li>
  </ul>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  props: {
      messages: {
          type: Array,
          default: []
      },
  }
})

export default class MessagesList extends Vue {}
</script>