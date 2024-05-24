<script lang="ts" setup>
import "./assets/main.css";
import "./assets/footer.css";
</script>
<template>
  <div>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"
    />
    <div class="container">
      <Header />
      <Main />
      <OurServices />
      <Companies />
    </div>
    <Footer />
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
