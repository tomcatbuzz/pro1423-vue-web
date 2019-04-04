<template>
  <v-carousel hide-delimiters>
    <v-carousel-item
      v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade"
        transition="fade"
    ></v-carousel-item>
  </v-carousel>
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

