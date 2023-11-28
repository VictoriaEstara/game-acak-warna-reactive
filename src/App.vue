<template>
  <div id="app" class="center-container">
    <div class="content">
      <!-- Ini kode yang mengatur reactive -->
      <div v-for="(color, index) in colors" :key="index" class="color-box" :style="{ backgroundColor: color }"></div>
      
      <!-- Ini kode yang memicu reactive -->
      <button @click="shuffleColors">Acak Warna</button>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        allColors: ['#F875AA', '#FFDFDF', '#22092C', '#001B79', '#A6CF98', '#7743DB', '#FF9130', '#FFC436', '#005B41'],
        colors: []
      };
    },

    mounted() {
      this.shuffleColors();
    },
    
    methods: {
      shuffleColors() {
        this.colors = this.shuffleArray(this.allColors).slice(0, 3);
      },
      
      shuffleArray(array) {
        let currentIndex = array.length, randomIndex;

        while (currentIndex !== 0) {
          randomIndex = Math.floor(Math.random() * currentIndex);
          currentIndex--;

          [array[currentIndex], array[randomIndex]] = [array[randomIndex], array[currentIndex]];
        }
        return array;
      }
    }
  };
</script>

<style>
  #app {

    background-color: #374259;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    text-align: center;
  }

  .center-container {
    width: 00px;
  }

  .color-box {
    width: 100px;
    height: 100px;
    margin: 10px;
    display: inline-block;
  }

  button {
    font-family: sans-serif;
    color: #331D2C;
    text-transform: uppercase;
    border: 3px solid transparent;
    border-radius: 999px;
    background-color: #FFF9C9;
    cursor: pointer;

    margin-top: 20px;
    padding: 10px;
    font-size: 16px;
    
  }
</style>