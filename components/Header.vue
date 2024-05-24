<template>
  <div data-collapse="medium" role="banner" class="navbar w-nav">
    <div class="nav-menu-wrapper">
      <a href="/" class="brand w-nav-brand" aria-label="home"
        ><img src="~/assets/images/logo.png" loading="lazy" height="100" alt=""
      /></a>
      <nav role="navigation" class="nav-menu w-nav-menu">
        <div class="menu-wrap">
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
              <p class="nav-item-title">Главная</p>
            </div>
          </div>
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
              <p class="nav-item-title">Каталог</p>
            </div>
          </div>
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
              <p class="nav-item-title">О нас</p>
            </div>
          </div>
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
              <p class="nav-item-title">Контакты</p>
            </div>
          </div>
        </div>
      </nav>
      <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
        <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
          <p class="nav-item-title">Русский</p>
        </div>
      </div>

      <div class="menu-button w-nav-button" role="button" @click="open">
        <img
          src="~/assets/images/gamburger.svg"
          height="16"
          class="image-burger"
        />
      </div>
    </div>

    <div v-if="isOpen" class="w-nav-overlay" @click="close"></div>
  </div>
</template>

<script setup>
const isOpen = ref(false);
const open = () => {
  isOpen.value = true;
};
const close = () => {
  isOpen.value = false;
};
</script>

<style lang="scss" scoped></style>
