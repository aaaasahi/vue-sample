<script setup lang="ts">
import { provide } from 'vue';
import Payment from './components/Payment.vue'
import Tweet from './components/Tweet.vue';
import { todos } from './useTodo'

provide('todos', todos)
</script>

<template>
  <!-- <Payment />
  <Tweet /> -->
  <TodoList />
</template>

<style scoped>
</style>
