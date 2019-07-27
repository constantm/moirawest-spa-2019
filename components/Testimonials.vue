<template>
  <div class="swiper w-100">
    <div class="swiper-container w-100 hidden md:block overflow-hidden">
      <!-- Additional required wrapper -->
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <div class="w-100 overflow-hidden relative">
            <div class="absolute h-full z-50 w-full flex">
              <div class="w-1/2 bg-white"></div>
            </div>

            <div class="absolute h-full z-50 w-full">
              <div class="container mx-auto h-full flex flex-wrap content-center">
                <div class="w-1/2">
                  <div class="pr-12 mr-12">
                    <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                    <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                    <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                  </div>
                  <Button href="#" title="More Kind Words" position="left" />
                </div>
              </div>
            </div>
            <div>
              <img class="w-full" src="https://moirawest.com/media/2018/03/Marise-Emile115.jpg" />
            </div>
          </div>
        </div>

        <div class="swiper-slide">
          <div class="w-100 overflow-hidden relative">
            <div class="absolute h-full z-50 w-full flex">
              <div class="w-1/2 bg-white"></div>
            </div>

            <div class="absolute h-full z-50 w-full">
              <div class="container mx-auto h-full flex flex-wrap content-center">
                <div class="w-1/2">
                  <div class="pr-12 mr-12">
                    <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                    <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                  </div>
                  <Button href="#" title="More Kind Words" position="left" />
                </div>
              </div>
            </div>
            <div>
              <img class="w-full" src="https://moirawest.com/media/2019/06/Jake-Jordy01.jpg" />
            </div>
          </div>
        </div>
      </div>

      <!-- If we need pagination -->
      <!-- <div class="swiper-pagination"></div> -->

      <!-- If we need navigation buttons -->
      <!-- <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>-->

      <!-- If we need scrollbar -->
      <!-- <div class="swiper-scrollbar"></div> -->
    </div>

    <div class="swiper-container w-100 md:hidden overflow-hidden">
      <!-- Additional required wrapper -->
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <div class="w-100 overflow-hidden relative">
            <div class="absolute h-full z-50 w-full flex">
              <div class="w-full bg-white"></div>
            </div>

            <div class="absolute h-full z-50 w-full">
              <div class="container mx-auto h-full flex flex-wrap content-center">
                <div class>
                  <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                  <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                  <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                </div>
                <Button href="#" title="More Kind Words" paddingY="py-6"/>
              </div>
            </div>
            <div>
              <img class="w-full" src="https://moirawest.com/media/2019/06/Anne-Ian072.jpg" />
            </div>
          </div>
        </div>

        <div class="swiper-slide">
          <div class="w-100 overflow-hidden relative">
            <div class="absolute h-full z-50 w-full flex">
              <div class="w-full bg-white"></div>
            </div>

            <div class="absolute h-full z-50 w-full">
              <div class="container mx-auto h-full flex flex-wrap content-center">
                <div class>
                  <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                  <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                </div>
                <Button href="#" title="More Kind Words" paddingY="py-6" />
              </div>
            </div>
            <div>
              <img class="w-full" src="https://moirawest.com/media/2019/06/Anne-Ian171.jpg" />
            </div>
          </div>
        </div>
      </div>

      <!-- If we need pagination -->
      <!-- <div class="swiper-pagination"></div> -->

      <!-- If we need navigation buttons -->
      <!-- <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>-->

      <!-- If we need scrollbar -->
      <!-- <div class="swiper-scrollbar"></div> -->
    </div>
  </div>

  <!-- <div class="row">
    <div class="image-block w-100 overflow-hidden relative">
      <div class="absolute h-full z-50 w-full flex">
        <div class="w-1/2 bg-white"></div>
      </div>

      <div class="absolute h-full z-50 w-full">
        <div class="container mx-auto h-full flex flex-wrap content-center">
          <div class="w-1/2">
            <div class="pr-12 mr-12">
                <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
                <p>Phasellus id turpis justo. Nunc imperdiet urna eget leo pellentesque mollis. Ut cursus nisi vel massa cursus dapibus.</p>
            </div>
            <Button href="#" title="More Kind Words" position="left"/>
          </div>
          
        </div>
      </div>

      <img
        class="w-full"
        v-parallax="0.3"
        src="https://moirawest.com/media/2018/03/Marise-Emile115.jpg"
        style="margin-bottom:-2em"
      />
    </div>
  </div>-->
</template>

<script>
import Swiper from "swiper";
import Button from "./Button";
export default {
  name: "Testimonials",
  components: { Button },
  props: {
    title: String,
    href: String
  },
  //   methods: {
  //       handleScroll(event) {

  //       }
  //   },
  //   created () {
  //     window.addEventListener('scroll', this.handleScroll);
  //   },
  //   destroyed () {
  //     window.removeEventListener('scroll', this.handleScroll);
  //   },
  mounted: function() {
    // const sliders = this.$el.children;
    // for (var i = 0, len = sliders.length; i < len; i++) {
    //   if (sliders[i].classList.contains("swiper")) {

    const sliders = this.$el.children;
    for (var i = 0, len = sliders.length; i < len; i++) {
      if (sliders[i].classList.contains("swiper-container")) {
        new Swiper(sliders[i], {
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

    // new Swiper(this.$el.firstChild, {
    //   loop: true,
    //   speed: 1300,
    //   effect: "fade",
    //   fadeEffect: {
    //     crossFade: false
    //   },
    //   autoplay: {
    //     disableOnInteraction: false,
    //     delay: 2000,
    //     waitForTransition: false
    //   }
    // });
  }
  // }
  //   }
};
</script>

<style scoped>
.bg-white {
  /* background: rgba(255, 255, 255, 0.4); */
  background: rgba(0, 0, 0, 0.5);
}
.image-block {
  height: 70vh;
}
</style>


