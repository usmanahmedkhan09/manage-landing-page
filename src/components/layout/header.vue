<template>
  <header class="header">
    <div class="header__logo">
      <logoIconVue></logoIconVue>
    </div>
    <ul class="header__list">
      <li>pricing</li>
      <li>product</li>
      <li>about us</li>
      <li>careers</li>
      <li>community</li>
    </ul>
    <div class="header__buttons">
      <button class="btn">Get Started</button>
    </div>
    <img
      class="header__pattren"
      src="../../assets/images/bg-tablet-pattern.svg"
      alt="header__pattren"
    />
    <menuIconVue
      @click="showMobileView = !showMobileView"
      class="header__menu"
    />
    <mobileMenuVue v-if="showMobileView" />
  </header>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
import logoIconVue from "../icons/logo-icon.vue";
import menuIconVue from "../icons/menu-icon.vue";
import mobileMenuVue from "./mobileMenu.vue";

export default defineComponent({
  components: { logoIconVue, menuIconVue, mobileMenuVue },
  setup() {
    const showMobileView = ref(false);
    return { showMobileView };
  },
});
</script>
