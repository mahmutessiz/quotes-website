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
  <HeaderSection class="z-10 sticky top-0" />
  <div class="flex w-full">
    <SideBar class="shadow-lg w-1/4" />
    <MainSection />
  </div>
  <FooterSection />
</template>
