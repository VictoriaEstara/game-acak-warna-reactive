## Gambaran Umum

Kode ini merupakan permainan sederhana tentang mengacak warna, terdapat 3 warna yang ditampilkan secara acak dengan memicu tombol yang muncul.

## Bahasa Pemrograman

Kode proyek ini ditulis menggunakan bahasa pemrograman JavaScript dengan framework vue.js.

## Software Pendukung

Proyek ini dikembangkan menggunakan [Visual Studio Code](https://code.visualstudio.com/download) dan memasang [Node.js](https://nodejs.org) V12+. Pastikan Anda memiliki kedua hal tersebut sebelum menjalankan proyek.

## Cara Penggunaan

Buka proyek Visual Studio Code atau coba bermain melalui [tautan](https://play.vuejs.org/#eNp9Vttu4zgM/RWO+9B0EadO0svEmw42TadAF9gLdhfYhyYPii3HamTJkOQ0mSL/PpR8L4pigAlNHorkoUj1zVvk+WhfUC/05oZmOSeGflsJgHnM9sDiu5VH8nzlQcSJ1vgVUWGo8iMpDGGCqpXn4JVDg0IzAhsjmr/4PjwJBjsZUzgSsYWMii0xhQJFSWTYnoLvt3h73N5PpMLjBpHkUg2BiZgeLvAHnEJjXuGOHhHhLN00rd3fSKsLtTlyiso32JBot1WyEPHSAsLyHDhhovNLjNiE/zTtjEXFx0lvCmOkgN8izqIdRtRpkSScumCY7bdFRHbwP1GCzC9LbM1eE72W5pedfuCnjhTLjYPQQy6VgZgmpOAG3sojYmLI4KL+AkwQuRXtNwDhvMwkhOfzs8evt9eLxfkQUHx8wH9OnEyC2WTpxCAY39/OnLi4WT7Ovjrx9vZq+nBfuc3G06ASl1fTm8rt+v5qfL4etoHLbmHUda07/VpKJ0SVUoZdMTTuVmBSpkc9CgcXHb+2Txk1qYwxQOP6zqvLgju1zAjuejEWSpHjwGkaqi5GGntJB8EQpnXwNnx7UXpHEPt/LyinBqJCKRyKJ3tVMbIDjTgOgUmHoIiIZeZsGKV1fE0ZpzDo+X65u4Ogdzx2u/XHs/8gJh0lXEo1cGJpRR5+6WXRFuS61LH4fi8LgGeX7nMXsx6WNTx3Yq/XGL3CdtU1tOe/7oQ/tWJ1cZ1Dy3jVd/tjL8/8shkIOxx2wt1snOG6ssyU8HbecWO5gT+b3l5NrmfVuTHTOGLHELB1lvdySthW+AynDy9Uue4qy0uhDUuObvmh/p01Y8JPKdumaBgHwT6t9IYejO8O7TlgJfZn9H6h1m19ZbFJQwiCvEyswdeb7R0QQ1ZIgE4ajS4jasswhXGraqpngmNof8NltOsGq9ZZFSjBFP2EZIyjiyZC+5oqllSHNfxOxw+TZbd2gxdB4yLPQijynKqIaFrZN1LFFL2m+QG05CwGB86JvSQ9jK9IzArsyGw2awr4oL2PuJSWdXvxtmmrzSWreO9y4RuZhzBp+chJHDOx7XHkitbsB0XtTaOtOMJL6C6eN/SMxg4mbDt60VLga+o4s+9QluMAq79yw6TAJ6DZUfiwci5ff3c6owpabzQvSmm0+0D/ovE1C1H4W1Fkfk9XXmMzWBHF99aav//7J9LeMWYyLjiiPzH+Q5H+wuZYwu6RU0y7g3PZPmX25UGO/tPfDzgDui7KJupIcfiVh39SLD8pvU13OppWZJ6800/ih7CO) ini secara online.

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
