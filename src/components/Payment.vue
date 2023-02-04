<template>
  <div class="container">
    <h1>最近の支出</h1>
    <div class="payment">
      <label>{{ item1 }}</label>
      <label>{{ price1 }}</label>
      <a :href="url">{{ url }}</a>
      <button @click="click('クリック！')">button</button>
    </div>
  </div>

</template>

<script setup lang="ts">

const item1 = "コーヒー"
const price1 = 300
const url = 'https://google.com'

const click = (itemName: string) => {
  window.alert(itemName)
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