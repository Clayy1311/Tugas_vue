<template>
  <div id="app">
    <h1>Vue Komponen</h1>
    <div class="components-container">
      <div class="component-wrapper">
        <Counter />
      </div>
      <div class="component-wrapper">
        <ColorChanger />
      </div>
      <div class="component-wrapper">
        <ImageCarousel />
      </div>
    </div>
  </div>
</template>

<script>
import Counter from './components/Counter.vue';
import ColorChanger from './components/ColorChanger.vue';
import ImageCarousel from './components/ImageCarousel.vue';

export default {
  name: 'App',
  components: {
    Counter,
    ColorChanger,
    ImageCarousel
  }
}
</script>

<style>
/* Reset some default styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  overflow-x: hidden; /* Prevent horizontal scrolling */
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: #f7f9fc; /* Light background color */
  color: #333; /* Text color */
  min-height: 100vh; /* Ensure the app takes up full viewport height */
  padding: 20px; /* Add padding to avoid content touching the edges */
}

h1 {
  color: #4a90e2; /* Heading color */
  margin-bottom: 20px;
  font-size: 2.5rem;
  font-weight: bold;
}

.components-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px; /* Spacing between components */
}

.component-wrapper {
  width: 100%;
  max-width: 600px; /* Limit width for better readability */
  background-color: #ffffff; /* White background for components */
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px;
  margin: 10px 0;
  transition: transform 0.3s, box-shadow 0.3s;
}

.component-wrapper:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

/* Responsive Design */
@media (max-width: 768px) {
  .components-container {
    flex-direction: column;
    gap: 15px; /* Adjust gap for smaller screens */
  }
}
</style>
