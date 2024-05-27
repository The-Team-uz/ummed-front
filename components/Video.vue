<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <div class="section without-bottom-spacing">
    <div class="section-title-wrapper">
      <h2 id="provide-assistance">{{ t("video-title") }}</h2>
      <div class="paragraph-large">
        {{ t("video-text") }}
      </div>
    </div>
    <div class="video-wrap" data-aos="fade-up">
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
.section {
  margin-top: 150px;
}
</style>
