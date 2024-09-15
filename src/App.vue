<template>
  <div id="app" class="app-container">
    <!-- Counter and Reset -->
    <div class="counter-section">
      <h1 class="text-2xl md:text-3xl">Counter</h1>
      <div class="counter-container">
        <button @click="decrement" class="btn">-</button>
        <span class="counter-value">{{ count }}</span>
        <button @click="increment" class="btn">+</button>
      </div>
      <button @click="reset" class="reset-button">Reset</button>
    </div>

    <!-- Color Changer -->
    <div class="color-changer">
      <h1 class="text-2xl md:text-3xl">Change Background Color</h1>
      <div class="color-buttons">
        <button v-for="color in colors" :key="color" :style="{ backgroundColor: color }" @click="changeColor(color)" class="color-button">
          {{ color }}
        </button>
      </div>
    </div>

    <!-- Carousel -->
    <Carousel />
  </div>
</template>

<script>
import Carousel from './components/Carousel.vue';

export default {
  name: 'App',
  components: {
    Carousel
  },
  data() {
    return {
      count: 0,
      colors: ['white', '#33FF57', '#3357FF', '#F1C40F', '#8E44AD']
    };
  },
  methods: {
    increment() {
      this.count += 1;
    },
    decrement() {
      if (this.count > 0) {
        this.count -= 1;
      }
    },
    reset() {
      this.count = 0;
    },
    changeColor(color) {
      document.body.style.backgroundColor = color;
    }
  }
};
</script>

<style>
/* General Styles */
html, body {
  height: 100%;
  margin: 0;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100vh;
  text-align: center;
  overflow: hidden;
}

/* Counter Section */
.counter-section {
  margin: 20px;
}

.counter-container {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-wrap: wrap;
}

.counter-value {
  font-size: 2em;
  color: brown;
}

.btn {
  padding: 10px 20px;
  font-size: 1.2em;
  cursor: pointer;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
}

/* Reset Button */
.reset-button {
  margin-top: 20px;
  background-color: red;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
}

/* Color Changer */
.color-changer {
  margin: 20px;
}

.color-buttons {
  display: flex;
  gap: 10px;
  justify-content: center;
  flex-wrap: wrap;
}

.color-button {
  color: white;
  border: none;
  border-radius: 5px;
  padding: 10px;
  font-size: 1em;
}
</style>
