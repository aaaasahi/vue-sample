<template>
  <div class="container">
    <h1>Tweeter</h1>
    <div class="form-container">
      <input v-model="inputDescription"/>
      <button @click="postTweet">post</button>
    </div>
    <div class="tweet-container">
      <ul>
        <p v-show="tweets.length <= 0">No tweets</p>
        <li v-for="tweet in tweets" class="tweet-list">
          <span>{{ tweet.description }}</span>
          <button @click="deleteTweet(tweet.id)" class="delete-button">delete</button>
        </li>
      </ul>
    </div>
  </div>

</template>

<script setup lang="ts">
import { ref } from 'vue'; 
const tweets = ref([{ id: 0, description: 'test' }])
const inputDescription = ref<string>('')

const postTweet = () => {
  if (inputDescription.value == '') return;
  const tweet = { id: Math.random(), description: inputDescription.value }
  tweets.value.push(tweet)
  inputDescription.value = ''
}

const deleteTweet = (id: number) => {
  console.log(id)
  tweets.value = tweets.value.filter(t => t.id !== id) 
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
}

ul {
  padding: 0;
}

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

button {
  background-color: black;
  color: white;
  margin-top: 10px;
  padding: 8px;
}

.delete-button {
  background-color: red;
  color: white;
}
</style>
