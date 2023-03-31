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
  <HeaderSection class="sticky -top-1 z-10" />

  <RouterView />

  <FooterSection />

  <!--   A journey of a thousand miles begins with a single step -->
</template>
