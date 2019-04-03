<template>
<div>
  <v-carousel hide-delimiters>
    <v-carousel-item
      v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade"
        transition="fade"
    ></v-carousel-item>
  </v-carousel>
  <div class="pt-5">
  <v-parallax
    dark
    src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    
  >
    <v-layout
      align-center
      column
      justify-center
    >
      <h1 class="display-2 font-weight-thin mb-3">Pro 1423</h1>
      <h4 class="subheading">Website Under Construction</h4>
      <h4 class="subheading">Coming Soon!</h4>
    </v-layout>
  </v-parallax>
  </div>
  </div>
</template>


<script>
  export default {
    data () {
      return {
        items: [
          {
            src: require('../assets/img/Runner.jpg')
          },
          {
            src: require('../assets/img/hearthand_y7s7k6.jpg')
          },
          {
            src: require('../assets/img/active-adult-athlete-348487.jpg')
          },
          {
            src: require('../assets/img/pexels-photo-460520.jpeg')
          }
        ]
      }
    }
  }
</script>
