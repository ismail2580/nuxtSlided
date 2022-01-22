<template>
  <transition>
    <div class="carouselSlides" v-show="visibleSlide === index">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  props: ["visibleSlide", "index"],
  data() {
    return {};
  },
};
</script>
