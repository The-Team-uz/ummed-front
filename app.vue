<script lang="ts" setup>
import "./assets/main.css";
</script>
<template>
  <div class="container">
    <Header />
    <Main />
    <OurServices />
    <Companies />
  </div>
</template>
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth !important;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
  display: flex;
  flex-direction: column;
}
</style>
