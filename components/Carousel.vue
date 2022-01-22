<template>
  <div class="carousel">
    <slot></slot>
    <div class="sliderAroweBtn">
      <img
        @click="prev"
        class="prev"
        src="./../static/Group 22prev.png"
        alt=""
      />
      <img @click="next" class="next" src="./../static/Group 23.png" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    prev() {
      this.$emit("prev");
    },
    next() {
      this.$emit("next");
    },
  },
};
</script>

<style scoped>
.carousel {
  position: relative;
  width: 100%;
  height: 90vh;
}
.sliderAroweBtn img {
  position: absolute;
  width: 50px;
  height: 50px;
  top: calc(50% - 20px);
}
.prev {
  left: 0;
}
.next {
  right: 0;
}
.sliderAroweBtn {
  display: flex;
  align-items: center;
  justify-content: space-between;
  align-content: center;
}
</style>
