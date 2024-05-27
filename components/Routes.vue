<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <section class="section overflow-hidden" data-aos="fade-up">
    <h1 class="mainword">{{ t("routes-title-main") }}</h1>
    <div class="services-carts">
      <div class="light-bgr-block">
        <div class="my-routes">
          <h2>{{ t("route1-title") }}</h2>
          <div class="image-right spacing">
            <img
              src="../assets/images/uzum.jpg"
              loading="lazy"
              alt="Uzum image"
              class="image-cover"
            />
          </div>
        </div>
        <a href="https://uzum.uz/ru/ummed" class="primary-button w-button">{{
          t("learn-more")
        }}</a>
      </div>

      <div class="light-bgr-block">
        <div class="my-routes">
          <h2>{{ t("route2-title") }}</h2>
          <div class="image-right spacing">
            <img
              src="../assets/images/partner.jpg"
              loading="lazy"
              alt=""
              class="image-cover"
            />
          </div>
        </div>
        <a href="https://linktr.ee/ummeduz" class="primary-button w-button">{{
          t("learn-more")
        }}</a>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.section {
  margin-top: 100px;
}

.image-cover {
  border-radius: 5px;
  margin-top: 10px;
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
</style>
