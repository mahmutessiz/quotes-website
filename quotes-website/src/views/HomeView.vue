<script>
import SideBar from "../components/SideBar.vue";

import MainSection from "../components/MainSection.vue";

export default {
  components: {
    SideBar,
    MainSection,
  },
};
</script>

<template>
  <div class="flex w-full">
    <SideBar class="hidden w-1/4 shadow-lg md:flex" />
    <MainSection />
  </div>
</template>
