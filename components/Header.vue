<script setup lang="ts">
const { t } = useI18n();
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
const i18n = useI18n();
const cookies = useCookie("lang", {
  watch: true,
});
const currentLang = ref(cookies.value);

const setLang = (lang: string) => {
  currentLang.value = lang;
  cookies.value = lang;
  i18n.setLocaleCookie(lang);
  i18n.setLocale(lang);
  isVisible.value = false;
};
window?.addEventListener("click", (e: Event) => {
  const target = e.target as HTMLElement;
  if (!target.closest("#language-bar")) {
    isVisible.value = false;
  }
});
</script>

<template>
  <div data-collapse="medium" role="banner" class="navbar w-nav" id="main">
    <!-- Font awesome -->
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"
    />

    <div class="">
      <div class="header-container">
        <a href="/" class="brand w-nav-brand" aria-label="home"
          ><img
            src="~/assets/images/logo.png"
            loading="lazy"
            height="130"
            alt=""
        /></a>
        <nav role="navigation" class="nav-menu w-nav-menu">
          <div class="menu-wrap">
            <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
              <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
                <a href="#main" class="nav-item-title">{{ t("main-menu") }}</a>
              </div>
            </div>
            <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
              <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
                <a href="#katalog" class="nav-item-title">{{ t("katalog") }}</a>
              </div>
            </div>
            <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
              <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
                <a href="#services" class="nav-item-title">{{ t("about") }}</a>
              </div>
            </div>
            <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
              <div class="nav-dropdown-toggle w-dropdown-toggle" role="button">
                <a href="#footer" class="nav-item-title">{{ t("contacts") }}</a>
              </div>
            </div>
          </div>
        </nav>
        <div style="display: flex; align-items: center">
          <div
            class="nav-dropdown-toggle w-dropdown-toggle"
            style="position: relative"
            id="language-bar"
          >
            <p
              class="nav-item-title"
              @click="isVisible = !isVisible"
              v-if="currentLang"
            >
              {{ t(currentLang) }}
              <i class="fa-solid fa-chevron-down"></i>
            </p>
            <div v-if="isVisible" class="languages_action">
              <div
                class="languages__action-item nav-item-title"
                @click="setLang('ru')"
              >
                Русский
              </div>
              <div
                class="languages__action-item nav-item-title"
                @click="setLang('uz')"
              >
                O'zbekcha
              </div>
            </div>
          </div>

          <div class="menu-button w-nav-button" role="button" @click="open">
            <img src="~/assets/images/gamburger.svg" class="image-burger" />
          </div>
        </div>
      </div>
    </div>
    <div v-if="isOpen" class="w-nav-overlay" @click="close">
      <nav role="navigation">
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
            <a href="#main" class="nav-item-title">{{ t("main-menu") }}</a>
          </div>
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <a href="#katalog" class="nav-item-title">{{ t("katalog") }}</a>
          </div>
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <a href="#services" class="nav-item-title">{{ t("about") }}</a>
          </div>
          <div class="nav-dropdown w-dropdown" style="max-width: 1200px">
            <a href="#footer" class="nav-item-title" @click="close">{{
              t("contacts")
            }}</a>
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.header-container {
  width: 100%;
  padding: 0 10px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
.languages_action {
  position: absolute;
  background-color: #fff;
  border: 1px solid #4444441e;
  border-radius: 5px;
  top: 60px;
  right: 22px;
  box-shadow: 0 0 2px 0.8px rgba(129, 129, 129, 0.2);
  .languages__action-item {
    padding: 5px;
  }
  .languages__action-item:hover {
    background-color: #f3f3f3;
  }
}
.fa-chevron-down {
  font-size: 12px;
}

* {
  scroll-behavior: smooth !important ;
}
</style>
