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
  </header>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import logoIconVue from "../icons/logo-icon.vue";

export default defineComponent({
  components: { logoIconVue },
  setup() {
    return {};
  },
});
</script>
