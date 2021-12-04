<template>
  <div class="product">
    <Header />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Product",
  components: {
    // HelloWorld,
    Header,
    Footer,
  },
};
</script>
