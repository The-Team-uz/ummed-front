<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/free-mode";
import "swiper/css/pagination";

import { FreeMode, Pagination, Autoplay } from "swiper/modules";
const modules = [Autoplay, Pagination, FreeMode];
</script>
<template>
  <div class="section about" style="margin-top: 100px">
    <div class="base-container w-container">
      <div class="section-title-wrapper">
        <h2 id="provide-assistance">
          Партнерские отношения, совместная работа, объединение знаний и опыта
          обеспечивают рост и развитие
        </h2>
      </div>
    </div>

    <Swiper
      :modules="modules"
      :slides-per-view="3"
      :space-between="20"
      :autoplay="{
        delay: 1500,
      }"
      class="swiper"
      :loop="true"
    >
      <SwiperSlide class="slide"
        ><img src="~/assets/images/1.jpg" alt="" />
      </SwiperSlide>
      <SwiperSlide class="slide">
        <img src="~/assets/images/2.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide">
        <img src="~/assets/images/3.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide">
        <img src="~/assets/images/4.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide">
        <img src="~/assets/images/6.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide">
        <img src="~/assets/images/7.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide">
        <img src="~/assets/images/8.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide"
        ><img src="~/assets/images/9.jpg" alt="" /></SwiperSlide
      ><SwiperSlide class="slide"
        ><img src="~/assets/images/10.jpg" alt=""
      /></SwiperSlide>
    </Swiper>
  </div>
</template>

<style lang="scss" scoped>
.swiper {
  width: 100%;
  .slide {
    height: 250px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fe552217;
    border-radius: 18px;
    border: 1px solid #4444443a;
    img {
      mix-blend-mode: multiply;
      width: 180px;
      object-fit: contain;
    }
  }
}
</style>
