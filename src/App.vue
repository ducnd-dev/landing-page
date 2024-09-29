<template>
  <div id="app" class="p-3 relative" style="background: linear-gradient(135deg, #E6FCFF 0%, #E0F0FF 54.9%, #E6F1FF 100%);">
    <div class="rounded-xl ">
      <header />
      <div class="absolute right-0 left-0 p-5 pt-40 rounded-xl mx-10 h-screen" :style="scrollCount <=1 ? 'background: linear-gradient(135.66deg, #00C7DE 4.06%, #0DA9EF 33.86%, #1A8CFF 56.73%, #1788FF 78.37%, #005DDE 100%);' : ''">
          <div v-if="scrollCount <= 1" data-aos="zoom-in" class="mt-40 relative flex justify-between container text-white pb-10">
            <div >
              <h2 class="font-semibold text-5xl"> Siêu nền tảng
                <vue-typer :text="['báo cáo', 'quản lý']" type-speed="100" back-speed="100" back-delay="1000" class="vue-custom" />
                  <br />
                toàn diện cho doanh nghiệp <br >
                quảng cáo meta.</h2>
                <p class="text-xl mt-8">SMIT Gate giúp bạn quản lý hiệu quả mọi khía cạnh của doanh nghiệp, <br>
                  trực quan hóa dữ liệu và báo cáo dễ dàng.</p>
            </div>
            <div class="relative h-12 w-36 flex items-center">
              <button class=" bg-white text-blue-900 font-semibold rounded-full p-3 z-10 text-nowrap">Dùng thử ngay</button>
              <div class="animate-ping absolute top-0 right-0 bottom-0 left-0 scale-50 bg-white rounded-full z-0"></div>
            </div>
          </div>
          <div v-if="scrollCount == 2" class="flex justify-center">
            <div class="relative" >
              <img src="./assets/hero.png"  data-aos="zoom-in" data-aos-duration="3500" alt="hero" class="" />
              <img src="./assets/curror-to-left.png" data-aos="zoom-fade-left" data-aos-anchor-placement="center-center" alt="hero" class=" absolute right-0 top-10" />
            </div>
          </div>
          <div v-if="scrollCount == 3" class="flex justify-center">
            <div class="relative">
              <img src="./assets/hero.png" alt="hero" class="w-[285px] h-[100px]" />
              <img src="./assets/curror-to-left.png" data-aos="zoom-fade-left" data-aos-anchor-placement="center-center" data-aos-duration="3500" alt="hero" class=" absolute right-10 top-0" />
            </div>
          </div>
          <div v-if="scrollCount == 3" class="flex justify-center my-10">
            <div>
              <img src="./assets/text.png" data-aos="zoom-in" data-aos-anchor-placement="center-center" data-aos-duration="2000" alt="hero" class="" />
            </div>
          </div>
          <div v-if="scrollCount == 3"  class="flex justify-center">
            <div data-aos="zoom-in" data-aos-duration="3500" >
              <img src="./assets/ui.png" alt="hero" class="" />
            </div>
          </div>
      </div>
    </div>
    <router-view />
    <footer />
  </div>
</template>
<script>
import { VueTyper } from 'vue-typer';
export default {
  components: {
    VueTyper,
  },
  data() {
    return {
      scrollCount: 0,
      isScrolling: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll(e) {
      if (this.isScrolling) return;

      this.isScrolling = true;

      if (this.scrollCount < 3) {
        window.scrollTo(0, 0);
        this.scrollCount++;
        console.log(`Scroll count: ${this.scrollCount}`);
      }

      switch (this.scrollCount) {
        case 1:
          // Action for the first scroll
          console.log('First scroll action');
          break;
        case 2:
          // Action for the second scroll
          console.log('Second scroll action');
          break;
        case 3:
          // Action for the third scroll
          console.log('Third scroll action');
          break;
        default:
          // Allow scrolling after the third scroll
          console.log('Scrolling allowed');
          break;
      }

      setTimeout(() => {
        this.isScrolling = false;
      }, 300); // Adjust the timeout duration as needed
    }
  }
};
</script>
<style scoped>
.vue-custom.vue-typer .custom.char {
  @apply text-white;
}

@keyframes ping-white {
  0% {
    transform: scale(1);
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    transform: scale(3.5);
    opacity: 0;
  }
}

.animate-ping-white {
  position: relative;
  display: inline-block;
  padding: 10px 20px;
  background-color: #3490dc;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  overflow: hidden;
}

.animate-ping-white::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 300%;
  height: 300%;
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  transform: translate(-50%, -50%) scale(1);
  animation: ping-white 2s infinite ease-in-out;
}
</style>