<template>
  <!-- Slider main container -->
  <div>
    <h1 class="logo absolute z-50 w-full top-1/2">
      <img
        class="mx-auto h-16"
        src="@/assets/moirawest_white@2x.png"
        alt="Moira West Photography"
      />
    </h1>

    <div class="swiper h-screen w-100 hidden md:block overflow-hidden">
      <div class="swiper-container h-screen w-100 hidden md:block">
        <div class="swiper-wrapper">
          <div
            v-for="image in slideshow_landscape"
            :style="backgroundImage(image)"
            :key="image.id"
            class="swiper-slide h-screen bg-center bg-no-repeat bg-cover"
          ></div>
        </div>
      </div>
    </div>

    <div class="swiper h-screen w-100 w-100 md:hidden overflow-hidden">
      <div class="swiper-container h-screen w-100 md:hidden">
        <div class="swiper-wrapper">
          <div
            v-for="image in slideshow_portrait"
            :key="image.id"
            :style="backgroundImage(image)"
            class="swiper-slide h-screen bg-center bg-no-repeat bg-cover"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from "swiper";
import Parallax from 'vue-parallaxy'

export default {
  name: "Swiper",
  props: {
    slideshow_landscape: Array,
    slideshow_portrait: Array,
    msg: String
  },
  components: {
    Parallax
  },
  methods: {
    backgroundImage(image){
      return `background-image: url(${image.filename})`;
    }
  },
  mounted: function() {
    const sliders = this.$el.children;
    for (var i = 0, len = sliders.length; i < len; i++) {
      if (sliders[i].classList.contains("swiper")) {
        new Swiper(sliders[i].firstChild, {
          loop: true,
          speed: 1300,
          effect: "fade",
          fadeEffect: {
            crossFade: false
          },
          autoplay: {
            disableOnInteraction: false,
            delay: 2000,
            waitForTransition: false
          }
        });
      }
    }
  }
};
</script>

<style>
@import "../node_modules/swiper/dist/css/swiper.css";
</style>
