<script setup lang="ts">
import "swiper/css";
import "swiper/css/free-mode";
import "swiper/css/pagination";
import { Swiper, SwiperSlide } from "swiper/vue";
import { FreeMode, Pagination, Autoplay } from "swiper/modules";

const { t } = useI18n();
const modules = [Autoplay, Pagination, FreeMode];
</script>
<template>
  <div class="section " style="margin-top: 100px">
    <div class="base-container w-container">
      <p class="title-11">
        {{ t("company-title") }}
      </p>
    </div>

    <Swiper
      :modules="modules"
      :slides-per-view="1"
      :space-between="20"
      :speed="5000"
      :autoplay="{
        delay: 0,
      }"
      class="swiper"
      :loop="true"
      :breakpoints="{
        '640': {
          slidesPerView: 2,
          spaceBetween: 20,
        },
        '1024': {
          slidesPerView: 3,
          spaceBetween: 40,
        },
      }"
    >
      <SwiperSlide class="slide"
        ><img src="~/assets/images/1.jpg" alt="" />
      </SwiperSlide>
      <SwiperSlide class="slide">
        <img src="~/assets/images/2.jpg" alt="" /> </SwiperSlide
      ><SwiperSlide class="slide">
        <img src="~/assets/images/3.jpg"  height="150" alt="" /> </SwiperSlide
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
@import "~/assets/_mixins.scss";
.section{
  width: 100%;
  padding: 0 10px;
}

.swiper {
  width: 100%;
  .slide {
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fe552217;
    border-radius: 18px;
    img {
      mix-blend-mode: multiply;
      width: 230px;
      object-fit: contain;
    }
  }
}
.title-11 {
  font-weight: 700 !important;
  color: #000 !important;
  line-height: 1em !important;
  font-size: 22px !important;
  width: 100% !important;
  text-align: center;
  margin-bottom: 30px;
  @include breakpoint(xs) {
    font-size: 25px !important;
  }

  @include breakpoint(md) {
    font-size: 30px !important;
  }

  @include breakpoint(lg) {
    font-size: 35px !important;
  }
}


</style>
<style>
.swiper-wrapper {
  -webkit-transition-timing-function: linear !important;
  transition-timing-function: linear !important;
}
</style>
