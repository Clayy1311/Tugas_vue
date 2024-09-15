<template>
    <div class="carousel-container">
      <h1>Image Carousel</h1>
      <div class="carousel">
        <img v-for="(image, index) in images" :key="index" :src="image.url" alt="Image" class="carousel-image" />
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: 'Carousel',
    data() {
      return {
        images: []
      };
    },
    methods: {
      fetchImages() {
        // Mengambil gambar dari API, gunakan API yang mengembalikan gambar acak
        axios.get('https://api.unsplash.com/photos/random?count=5&client_id=H4cYmWXt-suTNWlKY2rG4YSMvVgD6mnLiV122u4AXqo') // Ganti YOUR_ACCESS_KEY dengan kunci akses Unsplash Anda
          .then(response => {
            this.images = response.data.map(image => ({
              url: image.urls.small // Gunakan URL gambar ukuran kecil
            }));
          })
          .catch(error => {
            console.error('Error fetching images:', error);
          });
      }
    },
    created() {
      this.fetchImages(); // Ambil gambar saat komponen dibuat
    }
  };
  </script>
  
  <style>
  .carousel-container {
    margin-top: 20px;
  }
  
  .carousel {
    display: flex;
    overflow-x: auto;
    gap: 10px;
  }
  
  .carousel-image {
    width: 200px;
    height: 150px;
    object-fit: cover;
  }
  </style>
  