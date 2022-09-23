<template>
  <div class="container">
    <div
      v-for="(slide, index) in slides"
      :key="index" class="slide"
      :class="{ 'slide-active': index === activeIndex }"
      @click="changeSlide(index)"
    >
      <img :src="slide.image" :alt="slide.author" class="image">
      <span class="author" :class="{ 'author-active': index === activeIndex }"> {{ slide.author }} </span>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const activeIndex = ref(2)

const slides = [
  {
    image: 'https://images.unsplash.com/photo-1663324883004-593451448aa5?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDE4fDZzTVZqVExTa2VRfHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
    author: 'Rhameli'
  },
  {
    image: 'https://images.unsplash.com/photo-1663042446293-12f4d284a7c8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDM5fDZzTVZqVExTa2VRfHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
    author: 'Matt'
  },
  {
    image: 'https://images.unsplash.com/photo-1663269572021-7fc67e9ce3b9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDIwfDZzTVZqVExTa2VRfHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
    author: 'Marek'
  },
  {
    image: 'https://images.unsplash.com/photo-1662992672853-62155b6c3ceb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDI0fDZzTVZqVExTa2VRfHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
    author: 'Liam'
  },
  {
    image: 'https://images.unsplash.com/photo-1663038449536-8bc1bc2c9124?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDM2fDZzTVZqVExTa2VRfHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
    author: 'Andrew'
  },
]

const changeSlide = (index) => activeIndex.value = index
</script>

<style scoped>
.container {
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 0 5vw;
}

.slide {
  position: relative;
  width: max-content;
  height: 80vh;
  border-radius: 20px;
  margin: 10px;
  cursor: pointer;
  color: white;
  flex: 1;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  overflow: hidden;
  transition: all 500ms ease-in-out;
}

.image {
  height: 100%;
  border-radius: 20px;
}

.author {
  margin: 0;
  position: absolute;
  bottom: 20px;
  left: 20px;
  font-size: 24px;
  opacity: 0;
}

.slide-active {
  flex: 5;
}

.author-active {
  opacity: 1;
  transition: opacity 0.3s ease-in;
}
</style>
