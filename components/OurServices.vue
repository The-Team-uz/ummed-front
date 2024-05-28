<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <div
    id="services"
    class="section without-bottom-spacing"
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
          <h2>{{ t("service-title") }}</h2>
        </div>
        <p class="paragraph-large spacing">
          {{ t("service-text") }}
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@media (max-width: 500px) {
  .contacts-title h2 {
    font-weight: 700;
    color: #000;
    line-height: 1em;
    font-size: 30px;
  }
  .paragraph-large {
    font-size: 16px;
  }
}
</style>
