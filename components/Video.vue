<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <div class="section-1">
    <div class="t">
      <p class="title-11">{{ t("video-title") }}</p>

      <p class="title-22">{{ t("video-text") }}</p>
    </div>
    <div class="" data-aos="fade-up">
      <div class="background-video w-background-video w-background-video-atom">
        <video
          autoplay="true"
          loop="true"
          style="
            background-image: url('https://assets-global.website-files.com/64c23c6ec82b2204b21af185/64cd4a16f99de8f60cbd4081_production_id_4121618(720p)-poster-00001.jpg');
          "
          muted="true"
          playsinline="true"
        >
          <source src="~/assets/images/video1.mp4" data-wf-ignore="true" />
        </video>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "~/assets/_mixins.scss";
.section-1 {
  padding: 150px 10px 0;
  width: 100%;
  margin: 0 auto;
}
.background-video {
  height: 250px;
  @include breakpoint(sm) {
    height: 300px;
  }
  @include breakpoint(lg) {
    height: 500px;
  }
}
.t{
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
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
.title-22 {
  color: #676c80;
  margin-top: -20px;
  margin-bottom: 30px;
  line-height: 1.5em;
  // width: 100% !important;
  // width: 80%;

  text-align: center;
  font-size: 14px;
  @include breakpoint(xs){
    width: 500px;
  }
  @include breakpoint(md) {
    font-size: 20px;
    width: 780px;
  }
}
</style>
