<template>
  <div class="back">
    <div class="title">
      Репортажные съемки
    </div>

    <carousel :items-to-show="5" :wrapAround="true" :autoplay="2000" :pauseAutoplayOnHover="true">
      <slide v-for="slide in slides" :key="slide">
        <figure>
          <img :src="slide.image" class="image">
        </figure>
      </slide>

      <template #addons="{ slidesCount }">
        <Navigation v-if="slidesCount > 1"/>
      </template>
    </carousel>
  </div>
</template>

<script>
import 'vue3-carousel/dist/carousel.css'
import {Carousel, Slide, Navigation} from 'vue3-carousel'

export default {
  name: "reportComponent",
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data() {
    return {
      slides: [
        {
          image: require('@/assets/img/report/1.jpg')
        },
        {
          image: require('@/assets/img/report/2.jpg')
        },
        {
          image: require('@/assets/img/report/3.jpg')
        }
      ]
    }
  }
}
</script>

<style scoped>
.back {
  padding: 20px 60px;
  background-color: #032623;
}


.image {
  max-width: 300px;
}

.title {

  padding: 30px 0;
  color: white;
  font-size: 45px;
  font-family: Santello, sans-serif;
  letter-spacing: 2px;
}
</style>