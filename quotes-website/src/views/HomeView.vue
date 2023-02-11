<script>
import HeaderSection from "@/components/HeaderSection.vue";
import SideBar from "../components/SideBar.vue";
export default {
  components: {
    HeaderSection,
    SideBar,
  },
};
</script>

<template>
  <HeaderSection class="z-10 sticky top-0" />
  <SideBar class="shadow-lg" />
</template>
