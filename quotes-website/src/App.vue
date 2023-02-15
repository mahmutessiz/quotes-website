<script>
import { RouterView } from "vue-router";

import HeaderSection from "@/components/HeaderSection.vue";
import FooterSection from "@/components/FooteSection.vue";

export default {
  components: {
    HeaderSection,
    FooterSection,
    RouterView,
  },
};
</script>

<template>
  <HeaderSection class="sticky top-0 z-10" />

  <RouterView />

  <FooterSection />
</template>
