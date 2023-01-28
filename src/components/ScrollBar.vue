<template>
    <div>
      <img :src="currentImage.url" :style="{ 'border': '1px solid #ccc', 'box-shadow': '3px 3px 5px #ccc' }" class="responsive-img" @click="changeImage"/>
      <p class="caption" style="font-family: 'Bradley Hand', cursive; color: white; font-size: 22px;">{{ currentImage.date }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        images: [
        { url:  require('@/assets/1.jpg'), date: '11/12/2022' },
        { url:  require('@/assets/2.jpg'), date: '20/12/2022' },
        { url:  require('@/assets/3.jpg'), date: '20/12/2022' },
        { url:  require('@/assets/4.jpg'), date: '20/12/2022' },
        { url:  require('@/assets/5.jpg'), date: '29/12/2022' },
        { url:  require('@/assets/6.jpg'), date: '29/12/2023' },
        { url:  require('@/assets/11.jpg'), date: '07/01/2023' },
        { url:  require('@/assets/7.jpg'), date: '08/01/2023' },
        { url:  require('@/assets/8.jpg'), date: '08/01/2023' },
        { url:  require('@/assets/12.jpg'), date: '09/01/2023' },
        { url:  require('@/assets/13.jpg'), date: '16/01/2023' },
        { url:  require('@/assets/9.jpg'), date: '24/01/2023' },
        { url:  require('@/assets/10.jpg'), date: '24/01/2023' },
        { url:  require('@/assets/14.jpg'), date: '21/03/2022' },
        { url:  require('@/assets/15.jpg'), date: '21/03/2022' },
        ],
        currentImage: {},
        currentIndex: 0
      }
    },
    mounted() {
      this.currentImage = this.images[this.currentIndex]
      setInterval(() => {
      this.currentIndex = (this.currentIndex + 1) % this.images.length
      this.currentImage = this.images[this.currentIndex]
    }, 5000)
    },
    methods: {
      changeImage() {
        let currentIndex = this.images.indexOf(this.currentImage)
        let nextIndex = currentIndex + 1
        if (nextIndex >= this.images.length) {
          nextIndex = 0
        }
        this.currentImage = this.images[nextIndex]
        this.currentIndex = nextIndex
      },
    },
  }
  </script>
  
  <style>
  .responsive-img {
    max-width: 80%;
    height: auto;
    display: block;
    margin: 0 auto;
    margin-top: 10%;
  }
  
  .caption {
    text-align: center;
    margin-top: 10px;
  }
  </style>