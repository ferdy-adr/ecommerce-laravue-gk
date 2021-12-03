<template>
  <div class="home">
    <Header />
    <HeroSection />
    <BannerSection />
    <InstaSection />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from "@/components/Header.vue";
import HeroSection from "@/components/HeroSection.vue";
import BannerSection from "@/components/BannerSection.vue";
import InstaSection from "@/components/InstaSection.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld,
    Header,
    HeroSection,
    BannerSection,
    InstaSection,
  },
};
</script>
