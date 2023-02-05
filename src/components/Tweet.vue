<template>
  <div class="container">
    <h1>Tweeter</h1>
    <TweetPostFrom />
    <div class="tweet-container">
      <ul>
        <p v-show="tweets.length <= 0">No tweets</p>
        <TweetList :tweets="tweets"/>
      </ul>
    </div>
  </div>

</template>

<script setup lang="ts">
import { ref } from 'vue'; 

import TweetList from './TweetList.vue';
import TweetPostFrom from './TweetPostForm.vue'

const tweets = ref([{ id: 0, description: 'test' }])

// const postTweet = () => {
//   if (inputDescription.value == '') return;
//   const tweet = { id: Math.random(), description: inputDescription.value }
//   tweets.value.push(tweet)
//   inputDescription.value = ''
// }

// const deleteTweet = (id: number) => {
//   console.log(id)
//   tweets.value = tweets.value.filter(t => t.id !== id) 
// }
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
