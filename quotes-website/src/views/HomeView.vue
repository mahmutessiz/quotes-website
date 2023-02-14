<script>
import HeaderSection from "@/components/HeaderSection.vue";
import SideBar from "../components/SideBar.vue";
import FooterSection from "../components/FooteSection.vue";
import MainSection from "../components/MainSection.vue";

export default {
  components: {
    HeaderSection,
    SideBar,
    FooterSection,
    MainSection,
  },
};
</script>

<template>
  <HeaderSection class="sticky top-0 z-10" />
  <div class="flex w-full">
    <SideBar class="w-1/4 shadow-lg" />
    <MainSection />
  </div>
  <FooterSection />
</template>
