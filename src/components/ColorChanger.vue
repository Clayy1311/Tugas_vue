<template>
    <div>
      <div :style="{ backgroundColor: color }" class="color-box"></div>
      <button @click="changeColor">Ganti Warna</button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'ColorChanger',
    setup() {
      // Daftar warna yang lebih banyak
      const colors = [
        '#FF5733', // Red-Orange
        '#33FF57', // Lime Green
        '#3357FF', // Blue
        '#F4FF33', // Yellow
        '#FF33A6', // Pink
        '#FF8C33', // Dark Orange
        '#8CFF33', // Light Green
        '#33FFF4', // Cyan
        '#E5FF33', // Lime
        '#FF5733', // Coral
        '#5C33FF', // Purple
        '#FF33B5', // Magenta
        '#33FF6F', // Mint Green
        '#FF5733'  // Repeated color
      ];
      
      const color = ref(colors[0]);
      
      const changeColor = () => {
        const currentIndex = colors.indexOf(color.value);
        const nextIndex = (currentIndex + 1) % colors.length;
        color.value = colors[nextIndex];
      };
  
      return { color, changeColor };
    }
  }
  </script>
  
  <style>
  .color-box {
    width: 200px;
    height: 200px;
    margin-bottom: 10px;
    border: 1px solid #000;
  }
  </style>
  