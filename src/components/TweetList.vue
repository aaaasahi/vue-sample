<template>
<li v-for="tweet in tweets" class="tweet-list">
  <span>{{ tweet.description }}</span>
  <button @click="deleteTweet(tweet.id)" class="delete-button">delete</button>
</li>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';
type Tweet = {
  id: number,
  description: string
}

// オブジェクト型
type Props = {
  tweets: Tweet[]
}
// Tweet型を渡す
defineProps<Props>()

const deleteTweet = (id: number) => {
}

</script>

<style scoped>

.tweet-list {
  list-style: none;
  margin-bottom: 12px;
  border-radius: 4px;
  font-size: 12px;
  display: flex;
  justify-content: space-between;
  background-color: whitesmoke;
  padding: 8px 20px;
  width: 300px;
}

.delete-button {
  background-color: red;
  color: white;
}

</style>