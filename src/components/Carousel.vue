<script setup>
import { onMounted, onBeforeUnmount } from 'vue';

let carousel = null;

let carousel_images = [
    'images/1.jpg',
    'images/2.jpg',
    'images/3.jpg',
    'images/4.jpg',
    'images/5.jpg',
    'images/6.jpg'
  ]

onMounted(() => {
  carousel = new Flickity( '#carousel', {
    // options
  })
})
onBeforeUnmount(() => {
  carousel.destroy();
  console.log('onBeforeUnmounted : carousel')
  
})
</script>

<template>
  <div class="mx-auto items" id="carousel">
    <div :style="`background-image:url(${image})`" class="item" v-for="(image,index) in carousel_images" :key="index"></div>
  </div>
</template>


<style scoped>
.carousel_wrapper{
    width:600px;
    height:400px;
    margin:0 auto;
    background-color:#cfcfcf
  }
.items{
  width: 600px;
  height: 400px;
  margin: 0 auto;
}
.item{
  width: 600px;
  height:400px;
  background-color:#ccc;
  background-size:cover;
}
</style>