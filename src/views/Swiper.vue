<template>
  <v-container>
    <v-card class="swiper-inner">
      <!-- swiper -->
      <swiper :options="swiperOption">
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/1" /></swiper-slide>
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/2" /></swiper-slide>
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/3" /></swiper-slide>
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/8" /></swiper-slide>
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/5" /></swiper-slide>
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/6" /></swiper-slide>
        <swiper-slide><v-img src="http://lorempixel.com/600/600/sports/7" /></swiper-slide>
        <div slot="pagination" class="swiper-pagination" />
      </swiper>
    </v-card>
  </v-container>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      swiperOption: {
        effect: 'cube',
        grabCursor: true,
        cubeEffect: {
          shadow: true,
          slideShadows: true,
          shadowOffset: 20,
          shadowScale: 0.94
        },
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  }
}
</script>

<style scoped>
.swiper-inner {
    position: relative;
    overflow: hidden;
    height: 400px;
    padding: 15px;
  }
  .swiper-container {
    width: 300px!important;
    height: 300px;
    position: absolute;
    left: 50%;
    top: 50%;
    margin-left: -150px;
    margin-top: -150px;
  }
  .swiper-slide {
    background-position: center;
    background-size: cover;
  }
</style>
