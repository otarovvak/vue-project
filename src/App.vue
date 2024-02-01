<template>
  <div>
    <div class="card" v-for="(item) in arr" :key="item.name">
      <h3>{{ item.name }}</h3>
      <h5>{{ item.price }}</h5>
      <button  @click="item.amount > 0 ? item.amount-- : item.amount = 1" v-if="item.amount === 0">Buy</button>
      <div v-else :style="{ display: styleText }">
        <button @click="item.amount--">-</button>
        <span>{{ item.amount }}</span>
        <button @click="item.amount++">+</button>
    </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  import {ref} from 'vue';
  const styleText=ref('display:none')
  const arr=ref([
  {
    name: 'Бургер',
    price: 500,
    amount: 0
  },
  {
    name: 'Донер',
    price: 500,
    amount: 0

  },
  {
    name: 'Пицца',
    price: 500,
    amount: 0

  },
  {
    name: 'Рамен',
    price: 500,
     amount: 0

  },
  {
    name: 'Суши',
    price: 500,
    amount: 0

  }
]
)

</script>

<style scoped>

</style>