<script setup lang="ts">
const { t } = useI18n();
</script>

<template>
  <footer class="footer-two">
    <div class="footer-upper-section container">
      <div class="footer-flex">
        <div class="footer-about-column">
          <a href="/" class="navbar-brand w-nav-brand">
            <img
              src="../assets/images/ummedlogo.png"
              loading="lazy"
              alt="Brand Logo"
            />
          </a>

          <div>
            <p class="footer-about-text-two">
              From wellness tips to expert advice, we're here to support your
              journey to a healthier you.<br />
            </p>
            <div class="footer-soocial-link-wrapper">
              <a
                href="https://www.instagram.com/ummed_uz"
                target="_blank"
                class="social-link-block w-inline-block"
                title="Instagram"
              >
                <i class="fa-brands fa-instagram"></i>
              </a>
              <a
                href="https://www.facebook.com/ummeduz"
                target="_blank"
                class="social-link-block w-inline-block"
                title="Facebook"
              >
                <i class="fa-brands fa-facebook-f"></i>
              </a>
              <a
                href="https://t.me/ummedshop_uz"
                target="_blank"
                class="social-link-block w-inline-block"
                title="Telegram"
              >
                <i class="fa-brands fa-telegram"></i>
              </a>
              <!-- <a
                href="https://www.youtube.com/@Ummeduz"
                target="_blank"
                class="social-link-block w-inline-block"
                title="Youtube"
              >
                <i class="fa-brands fa-youtube"></i>
              </a> -->
              <a
                :href="`mailto:ummed.info@mail.ru`"
                target="_blank"
                class="social-link-block w-inline-block"
                title="Email"
              >
                <i class="fa-regular fa-envelope"></i>
              </a>
              <a
                href="https://t.me/ummed_uz"
                target="_blank"
                class="social-link-block w-inline-block"
                title="Admin"
              >
                <i class="fa-regular fa-user"></i>
              </a>
            </div>
          </div>
        </div>

        <div>
          <div class="footer-heading">{{ t("worktime") }}</div>
          <div class="opening-hours-wrapper">
            <div class="opening-hours-item">
              <div class="opening-hours-text-two">{{ t("workdays") }}</div>
              <div class="opening-hours-text-two">09:00 - 20:00</div>
            </div>
            <div class="opening-hours-text-two">
              {{ t("obed") }} 13:00 - 14:00
            </div>
            <div class="opening-hours-item">
              <div class="opening-hours-text-two">{{ t("freeday") }}</div>
            </div>
          </div>
        </div>

        <div>
          <div class="footer-heading">{{ t("contact") }}</div>
          <div class="footer-contact-wrapper">
            <p class="footer-text-two">
              {{ t("location") }}
            </p>
            <a href="tel:+1500321852789" class="footer-text-link-two">
              +998 95 501 07 07
            </a>
            <a :href="`mailto:ummed.info@mail.ru`" class="footer-text-link-two"
              >ummed.info@mail.ru</a
            >
          </div>
        </div>
      </div>
    </div>

    <!-- Footer bottom -->
    <div class="footer-lower-section">
      <div class="w-layout-blockcontainer container-fluid w-container">
        <div class="footer-line-two"></div>
        <div class="footer-copyright-text-two">
          © “Ummed”, 2024 - {{ t("footer") }}
        </div>
      </div>
    </div>
    <!-- <div>
      <img
        src="https://assets-global.website-files.com/6551ed212e2ea32fb46bb7c8/655b135120eb4c16ccf8b1f1_highlighter-shape-11.svg"
        loading="lazy"
        alt="Footer Highlighter Shape 1"
        class="footer-highlighter-shape-one"
      /><img
        src="https://assets-global.website-files.com/6551ed212e2ea32fb46bb7c8/6558423457c432bd2be26543_highlighter-shape-4.svg"
        loading="lazy"
        alt="Footer Highlighter Shape 2"
        class="footer-highlighter-shape-2"
      />
    </div> -->
  </footer>
</template>

<style lang="scss" scoped>
.footer-two {
  margin-top: 150px;
  padding: 0 30px;
}
</style>
