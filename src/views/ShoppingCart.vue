<template>
  <div class="shopping-cart">
    <Header />

    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "ShoppingCart",
  components: {
    Header,
    Footer,
  },
};
</script>