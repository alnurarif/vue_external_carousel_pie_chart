<script setup>
import { onMounted, ref } from 'vue';
import Carousel from './components/Carousel.vue'
import Piechart from './components/Piechart.vue'

let hoverActiveCarousel = ref(false)
let hoverActivePiechart = ref(false)
let tabActive = ref('')

onMounted(() => {
  tabActive.value = 'carousel'
})

</script>

<template>
  <div class="tab_holder">
    <button class="tab_button" @click="tabActive='carousel'" @mouseover="hoverActiveCarousel=true" @mouseleave="hoverActiveCarousel=false" :class="{tab_active : hoverActiveCarousel || tabActive=='carousel'}">Carousel</button>
    <button class="tab_button" @click="tabActive='piechart'" @mouseover="hoverActivePiechart=true" @mouseleave="hoverActivePiechart=false" :class="{tab_active : hoverActivePiechart || tabActive=='piechart'}">PieChart</button>
  </div>
  
  <Carousel v-if="tabActive=='carousel'"/>
  <Piechart v-if="tabActive=='piechart'"/>
</template>

<style scoped>
.tab_active{
  background: #46c7be !important;
}
.tab_holder{
  width: 600px;
  margin: 10px auto;
  height:50px;
  background:#84e5ef
}
.tab_button{
  float:left;
  width:50%;
  height:50px;
  font-weight: 500;
}
.carousel_wrapper{
  width:600px;
  height:400px;
  margin:0 auto;
  background-color:#cfcfcf
}
.item{
  height:400px;
  width:600px;
}
</style>
