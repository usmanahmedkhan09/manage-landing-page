<template>
  <layoutComponentVue />
</template>
<script lang="ts">
import { defineComponent } from "vue";
import layoutComponentVue from "@/components/layout/index.vue";

export default defineComponent({
  components: { layoutComponentVue },
  setup() {
    return {};
  },
});
</script>
