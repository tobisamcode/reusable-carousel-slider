<template>
  <div class="home">
    <Carousel>
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