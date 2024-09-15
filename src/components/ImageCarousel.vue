<template>
    <div>
      <img :src="images[currentIndex]" alt="carousel image" class="carousel-image"/>
      <button @click="prevImage">Prev</button>
      <button @click="nextImage">Next</button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'ImageCarousel',
    setup() {
      const baseUrl = 'https://picsum.photos';
      const imageSizes = [
        '300/200',
        '300/300',
        '300/400'
      ];
      
      // Generate random IDs for images
      const generateRandomId = () => Math.floor(Math.random() * 1000);
  
      const images = [
        `${baseUrl}/${imageSizes[0]}?random=${generateRandomId()}`,
        `${baseUrl}/${imageSizes[1]}?random=${generateRandomId()}`,
        `${baseUrl}/${imageSizes[2]}?random=${generateRandomId()}`
      ];
  
      const currentIndex = ref(0);
  
      const nextImage = () => {
        currentIndex.value = (currentIndex.value + 1) % images.length;
      };
  
      const prevImage = () => {
        currentIndex.value = (currentIndex.value - 1 + images.length) % images.length;
      };
  
      return { images, currentIndex, nextImage, prevImage };
    }
  }
  </script>
  
  <style>
  .carousel-image {
    width: 300px;
    height: 200px;
  }
  </style>
  