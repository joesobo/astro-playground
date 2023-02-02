<template>
  <div>
    <h3>{{ greeting }}! Thank you for visiting!</h3>
    <button @click="setGreeting(randomMessage())">New Greeting</button>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const props = defineProps<{ messages: string[] }>();

const randomMessage = () => {
  const randomIndex = Math.floor(Math.random() * props.messages.length);
  return props.messages[randomIndex];
};

const greeting = ref(randomMessage());

const setGreeting = (newGreeting: string) => {
  greeting.value = newGreeting;
};
</script>
