<template>
  <footer class="footer">
    <div class="logo_wrapper">
      <Logo class="logo" />
      <div class="social-icons">
        <IconYouTube />
        <IconFaceBook />
        <IconTwitter />
        <IconInstagram />
        <IconPrinterest />
      </div>
    </div>
    <ul role="list">
      <li>About Us</li>
      <li>Contact</li>
      <li>Blog</li>
    </ul>
    <ul role="list">
      <li>Careers</li>
      <li>Support</li>
      <li>Privacy Policy</li>
    </ul>
    <div class="button_wrapper">
      <div class="input__wrapper">
        <input type="text" placeholder="Updates in your inbox..." />
        <button class="btn">Go</button>
      </div>
      <p class="rights">Copyrights 2020. All Rights Reserved</p>
    </div>
  </footer>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import Logo from "@/components/icons/logo-icon.vue";
import IconYouTube from "@/components/icons/icon-youtube.vue";
import IconFaceBook from "@/components/icons/icon-facebook.vue";
import IconTwitter from "@/components/icons/icon-twitter.vue";
import IconInstagram from "@/components/icons/icon-instagram.vue";
import IconPrinterest from "@/components/icons/icon-pinterest.vue";

export default defineComponent({
  components: {
    Logo,
    IconYouTube,
    IconFaceBook,
    IconTwitter,
    IconInstagram,
    IconPrinterest,
  },
  setup() {
    return {};
  },
});
</script>
