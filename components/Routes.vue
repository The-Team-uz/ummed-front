<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <section class="section overflow-hidden" data-aos="fade-up" id="katalog">
    <p class="title-11">{{ t("routes-title-main") }}</p>
    <div class="services-carts">
      <div class="light-bgr-block">
        <div class="my-routes">
          <p class="title-11">{{ t("route1-title") }}</p>
          <!-- <div class="image-right spacing"> -->
          <img
            src="../assets/images/uzum.jpg"
            loading="lazy"
            alt="Uzum image"
            class="image-cover"
          />
          <!-- </div> -->
        </div>
        <a href="https://uzum.uz/ru/ummed" class="primary-button w-button">{{
          t("learn-more")
        }}</a>
      </div>

      <div class="light-bgr-block">
        <div class="my-routes">
          <p class="title-11">{{ t("route2-title") }}</p>
          <!-- <div class="image-right spacing"> -->
          <img
            src="../assets/images/partner.jpg"
            loading="lazy"
            alt=""
            class="image-cover"
          />
          <!-- </div> -->
        </div>
        <a href="https://linktr.ee/ummeduz" class="primary-button w-button">{{
          t("learn-more")
        }}</a>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "~/assets/_mixins.scss";
.section {
  width: 100%;
  padding: 150px 10px 0;
}

.image-cover {
  border-radius: 5px;
  margin-top: 10px;
  mix-blend-mode: multiply;
  height: 200px;
  @include breakpoint(xs) {
    height: 250px;
  }
  @include breakpoint(sm) {
    height: 450px;
  }
  @include breakpoint(lg) {
    height: 350px;
  }
}

.my-routes {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  h2 {
    font-weight: normal;
    font-size: 35px;
  }
}

.primary-button {
  margin-top: 30px;
  background-color: #fe5722;
  border-color: #fe5722;
}

.primary-button:hover {
  background-color: #fff;
  border-color: #000;
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
