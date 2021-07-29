<template>
  <div class="home">
    <Carousel class="carousel">
      <slide>
        <div>Hello</div>
      </slide>
    </Carousel>
  </div>
</template>

<script>
import Carousel from '../components/Carousel.vue';
import Slide from '../components/Slide.vue';


export default {
  name: 'Home',
  components: {
    Carousel,
    Slide
  }
}
</script>

<style lang="scss" scoped>
  .carousel{
    max-height: 100vh;
    height: 100vh;
  }
</style>