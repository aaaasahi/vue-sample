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
      <label>{{ priceLabel }}</label>
      <a :href="url">{{ url }}</a>
      <button @click="click('クリック！')">button</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive, computed, onBeforeMount, onMounted, onUpdated } from 'vue';

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

const budget = 5000

// 関数でも書けるが計算ロジックなどはcomputed推奨
const priceLabel = computed(() => {
  return item1.price > budget ?  'too expensive' : item1.price
})

// ライフサイクル https://v3.ja.vuejs.org/api/options-lifecycle-hooks.html#beforecreate
// 読み込み時
onBeforeMount(() => {
  console.log('before mount')
})

// 読み込み時
onMounted(() => {
  console.log('mounted')
})

// inputに入力、clearボタン押した時
onUpdated(() => {
  console.log('update')
})

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