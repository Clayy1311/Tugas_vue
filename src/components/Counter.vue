<template>
    <div>
      <h2>Counter: {{ count }}</h2>
      <button @click="increment">Tambah</button>
      <button @click="decrement">Kurang</button>
      <button @click="reset">Reset</button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'Counter',
    setup() {
      const count = ref(0);
  
      const increment = () => count.value++;
      const decrement = () => count.value--;
      const reset = () => count.value = 0;
  
      return { count, increment, decrement, reset };
    }
  }
  </script>
  