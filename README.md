## Gambaran Umum

Kode ini merupakan permainan sederhana tentang mengacak warna, terdapat 3 warna yang ditampilkan secara acak dengan memicu tombol yang muncul.

## Bahasa Pemrograman

Kode proyek ini ditulis menggunakan bahasa pemrograman JavaScript dengan framework vue.js.

## Software Pendukung

Proyek ini dikembangkan menggunakan [Visual Studio Code](https://code.visualstudio.com/download) dan memasang [Node.js](https://nodejs.org) V12+. Pastikan Anda memiliki kedua hal tersebut sebelum menjalankan proyek.

## Cara Penggunaan

1. Buka proyek menggunakan Dev-C++.
2. Jalankan aplikasi dengan melakukan compile dan Run (shortcut F11).
4. Ikuti petunjuk untuk memasukkan data array.
5. Kemudian tekan 'enter' untuk menghitung dan menampilkan nilai maksimal dan minimal dari data array, serta menghitung jumlah data array yang dimasukkan.

## Contoh Penggunaan Program

```vue
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
