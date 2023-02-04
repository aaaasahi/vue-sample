<template>
  <div class="container">
    <h1>最近の支出</h1>
    <!-- 同じ意味 -->
    <input @input="input1" :value="item1.name">
    <input v-model="item1.price">
    <!-- 　　　　 -->
    <button @click="clear">clear</button>
    <div class="payment">
      <label>{{ item1.name }}</label>
      <label>{{ item1.price }}</label>
      <a :href="url">{{ url }}</a>
      <button @click="click('クリック！')">button</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue';

// 単一の値の場合はrefオブジェクトごとの場合はreactive

// const item1 = ref<string>('a')

const item1 = reactive({
  name: '',
  price: 0
})

const url = 'https://google.com'

const click = (itemName: string) => {
  window.alert(itemName)
}

const input1 = (e: any) => {
  item1.name = e.target.value
}

const input2 = (e: any) => {
  item1.price = e.target.value
}

const clear = () => {
  item1.name = '',
  item1.price = 0
}

</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  flex-direction: column;
}

.payment {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  width: 400px;
  background-color: whitesmoke;
}

label {
  font-size: 20px;
  font-weight: bold;
}

button {
  background-color: black;
  color: white;
}

</style>