<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <div
    id="services"
    class="services"
    style="margin-top: 150px"
  >
    <div class="home-contacts-wrapper about">
      <div data-aos="fade-left" class="block-benefits about">
        <div class="row-benefit">
          <div class="image-row">
            <img
              src="../assets/images/25years.webp"
              loading="lazy"
              width="34"
              height="34"
              alt=""
            />
          </div>
          <div class="text-row">
            <h4>{{ t("service1-title") }}</h4>
            <div>{{ t("service1-text") }}</div>
          </div>
        </div>
        <div class="row-benefit">
          <div class="image-row">
            <img
              src="../assets/images/fast.png"
              loading="lazy"
              width="34"
              height="34"
              alt=""
            />
          </div>
          <div class="text-row">
            <h4>{{ t("service2-title") }}</h4>
            <div>{{ t("service2-text") }}</div>
          </div>
        </div>
        <div class="row-benefit">
          <div class="image-row">
            <img
              src="../assets/images/proteam.jpg"
              loading="lazy"
              width="34"
              height="34"
              alt=""
            />
          </div>
          <div class="text-row">
            <h4>{{ t("service3-title") }}</h4>
            <div>{{ t("service3-text") }}</div>
          </div>
        </div>
      </div>
      <div style="opacity: 1" class="home-contacts-content">
        <div class="contacts-title">
          <p class="title-11">{{ t("service-title") }}</p>
        </div>
        <p class="title-22">
          {{ t("service-text") }}
        </p>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
@import "~/assets/_mixins.scss";
.services{
  width: 100%;
  padding: 0 10px;
}
.title-11 {
  font-weight: 700 !important;
  color: #000 !important;
  line-height: 1em !important;
  font-size: 22px !important;
  width: 100% !important;
  // text-align: center;
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
.title-22 {
  color: #676c80;
  margin-top: -10px;
  margin-bottom: 30px;
  line-height: 1.5em;
  width: 100% !important;
  // text-align: center;
  font-size: 14px;
  @include breakpoint(md) {
    font-size: 20px;
  }
}
</style>
