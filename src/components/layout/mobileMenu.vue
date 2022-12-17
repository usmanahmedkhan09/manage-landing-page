<template>
  <div class="mobileMenu">
    <crossIconVue @click="$emit('toggleMenu')" class="mobileMenu__crossIcon" />
    <div class="mobileMenu__card">
      <ul class="mobileMenu__card--list">
        <li>pricing</li>
        <li>product</li>
        <li>about us</li>
        <li>careers</li>
        <li>community</li>
      </ul>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import crossIconVue from "../icons/cross-icon.vue";

export default defineComponent({
  components: { crossIconVue },
  setup() {
    return {};
  },
});
</script>
