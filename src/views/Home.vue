<template>
  <div class="home">
    <Header />
    <HeroSection />
    <BannerSection />
    <InstaSection />
    <PartnerLogoSection />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from "@/components/Header.vue";
import HeroSection from "@/components/HeroSection.vue";
import BannerSection from "@/components/BannerSection.vue";
import InstaSection from "@/components/InstaSection.vue";
import PartnerLogoSection from "@/components/PartnerLogoSection.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld,
    Header,
    HeroSection,
    BannerSection,
    InstaSection,
    PartnerLogoSection,
    Footer,
  },
};
</script>
