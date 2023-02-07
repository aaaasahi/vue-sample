<script setup lang="ts">
import { provide } from 'vue';
import Payment from './components/Payment.vue'
import Tweet from './components/Tweet.vue';
import { todos, todoKey } from './useTodo'

provide(todoKey, todos)
</script>

<template>
  <!-- <Payment />
  <Tweet /> -->
  <TodoList />
</template>

<style scoped>
</style>
