<template>
<div class="form-container">
  <input v-model="inputDescription"/>
  <button class="save" @click="postTweet">post</button>
</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'; 
import { defineEmits } from 'vue';

const emit = defineEmits(['post-tweet'])
const inputDescription = ref<string>('')

const postTweet = () => {
  emit('post-tweet', inputDescription.value)
  inputDescription.value = ''
}

</script>

<style scoped>
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

.save {
  background-color: black;
  color: white;
  margin-top: 10px;
  padding: 8px;
}

</style>
