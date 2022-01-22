<template>
  <div class="carousel">
     <carousel @prev="prev" @next="next">
      <carousel-slides
        v-for="(slide, index) in slides"
        :key="slide"
        :index="index"
        :visibleSlide="visibleSlide"
      >
        <img :src="slide" alt="" />
      </carousel-slides>
    </carousel>
  </div>
</template>

<script>
import carousel from "../components/Carousel.vue";
import CarouselSlides from '../components/carouselSlides.vue';
export default {
  data() {
    return {
      slides: [
        "https://picsum.photos/seed/picsum/600/350",
        "https://picsum.photos/id/237/600/350",
        "https://picsum.photos/600/350?grayscale",
        "https://picsum.photos/600/350/?blur",
        "https://picsum.photos/600/350.jpg"
      ],
      visibleSlide: 0,
    };
  },
  computed: {
    slidesLen() {
      return this.slides.length;
    },
  },
  methods: {
    next() {
      if (this.visibleSlide >= this.slidesLen.length + 1) {
        this.visibleSlide = 0;
      } else if (this.visibleSlide===4) {
        this.visibleSlide = 0
      } else {
        this.visibleSlide++;
      }
    },
    prev() {
      if (this.visibleSlide=== 1) {
        this.visibleSlide= 4
       
      }else if (this.visibleSlide <= 1)  {
        this.visibleSlide = 4
         console.log(this.visibleSlide)
      }
       else {
        this.visibleSlide--;
      }
    },
  },
  name: "IndexPage",
  components: { carousel, CarouselSlides },
}
</script>
<style>
*{
  margin: 0;
  padding: 0;
}
.carouselSlides img {
  width: 100%;
  height: 90vh;
}
</style>