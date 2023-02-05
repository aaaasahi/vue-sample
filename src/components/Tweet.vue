<template>
<div class="container">
  <h1>Tweeter</h1>
  <TweetPostFrom @post-tweet="postTweet"/>
  <div class="tweet-container">
    <ul>
      <p v-show="tweets.length <= 0">No tweets</p>
      <TweetList :tweets="tweets" @delete-tweet="deleteTweet"/>
    </ul>
  </div>
</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'; 

import TweetList from './TweetList.vue';
import TweetPostFrom from './TweetPostForm.vue'

const tweets = ref([{ id: 0, description: 'test' }])

const postTweet = (description: string) => {
  if (description == '') return;
  const tweet = { id: Math.random(), description }
  tweets.value.push(tweet)
}

const deleteTweet = (id: number) => {
  tweets.value = tweets.value.filter(t => t.id !== id) 
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

ul {
  padding: 0;
}
</style>
