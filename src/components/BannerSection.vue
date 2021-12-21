<template>
  <!-- Women Banner Section Begin -->
  <section class="women-banner spad">
    <div class="container-fluid">
      <div class="row">
        <!-- show carousel if product found -->
        <div class="col-lg-12 mt-5" v-if="products.length > 0">
          <carousel
            class="product-slider"
            :items="3"
            :nav="false"
            :autoplay="true"
            :loop="false"
            :dots="false"
          >
            <div
              class="product-item"
              v-for="itemProduct in products"
              v-bind:key="itemProduct.id"
            >
              <div class="pi-pic">
                <img v-bind:src="itemProduct.galleries[0].photo" alt="" />
                <ul>
                  <li class="w-icon active">
                    <a href="#"><i class="icon_bag_alt"></i></a>
                  </li>
                  <li class="quick-view">
                    <!-- <a href="product.html">+ Quick View</a> -->
                    <router-link to="/product">+ Quick View</router-link>
                  </li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">{{ itemProduct.type }}</div>
                <a href="#">
                  <h5>{{ itemProduct.name }}</h5>
                </a>
                <div class="product-price">
                  {{ itemProduct.price }}
                  <span>£125.00</span>
                </div>
              </div>
            </div>
          </carousel>
        </div>

        <!-- if the product is not found -->
        <div class="col-lg-12 mt-5" v-else>
          <p>Produk belum tersedia untuk saat ini</p>
        </div>
      </div>
    </div>
  </section>
  <!-- Women Banner Section End -->
</template>

<script>
import carousel from "vue-owl-carousel";
import axios from "axios";

export default {
  name: "BannerSection",
  components: {
    carousel,
  },
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    axios
      .get("http://127.0.0.1:8000/api/product")
      .then((res) => (this.products = res.data.data.data))
      // eslint-disable-next-line no-console
      .catch((err) => console.log(err));
  },
};
</script>

<style scoped>
.product-item {
  margin-right: 25px;
}
</style>