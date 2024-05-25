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
      <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
        <p class="nav-item-title" @click="isVisible = !isVisible">Русский</p>
        <div v-if="isVisible" class="languages_action">
          <div class="languages__action-item nav-item-title" >
            Русский
          </div>
          <div class="languages__action-item nav-item-title" >
            O'zbekcha
          </div>
          
        </div>
      </div>

      <div class="menu-button w-nav-button" role="button" @click="open">
        <img src="~/assets/images/gamburger.svg" class="image-burger" />
      </div>

      <div v-if="isOpen" class="w-nav-overlay" @click="close">
        <nav role="navigation" @click.stop.prevent>
          <div class="tablet-menu">
            <a href="/" class="brand-tablet w-nav-brand" aria-label="home"
              ><img src="~/assets/images/logo.png" width="85" alt=""
            /></a>
            <div
              class="close-menu-button w-nav-button w--open"
              role="button"
              @click="close"
            >
              <img
                src="https://assets-global.website-files.com/64c23c6ec82b2204b21af185/64c23c6fc82b2204b21af2a5_close-btn.svg"
                alt="icon"
                class="nav-close-icon"
              />
            </div>
          </div>
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
      </div>
    </div>
  </div>
</template>

<script setup>
const isOpen = ref(false);
const isVisible = ref(false);
const open = () => {
  document.body.style.overflow = "hidden";
  isOpen.value = true;
};
const close = () => {
  document.body.style.overflow = "auto";
  isOpen.value = false;
};
</script>

<style lang="scss" scoped></style>
