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
    <SideBar class="w-1/4 shadow-lg" />
    <MainSection />
  </div>
</template>
