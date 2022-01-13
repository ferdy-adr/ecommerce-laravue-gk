<template>
  <div class="product">
    <Header />

    <!-- Breadcrumb Section Begin -->
    <div class="breacrumb-section text-left">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="breadcrumb-text product-more">
              <router-link to="/"><i class="fa fa-home"></i> Home</router-link>
              <span>Detail</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Breadcrumb Section Begin -->

    <!-- Product Shop Section Begin -->
    <section class="product-shop spad page-details">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="row">
              <div class="col-lg-6">
                <div class="product-pic-zoom">
                  <img class="product-big-img" :src="mainImage" alt="" />
                </div>
                <div class="product-thumbs">
                  <carousel
                    :nav="false"
                    :dots="false"
                    class="product-thumbs-track ps-slider"
                  >
                    <div
                      class="pt"
                      @click="changeImage(thumbs[0])"
                      :class="thumbs[0] == mainImage ? 'active' : ''"
                    >
                      <img
                        src="img/products/jacket/lyle-scott-jacket-1.jpg"
                        alt=""
                      />
                    </div>

                    <div
                      class="pt"
                      @click="changeImage(thumbs[1])"
                      :class="thumbs[1] == mainImage ? 'active' : ''"
                    >
                      <img
                        src="img/products/jacket/lyle-scott-jacket-2.jpg"
                        alt=""
                      />
                    </div>

                    <div
                      class="pt"
                      @click="changeImage(thumbs[2])"
                      :class="thumbs[2] == mainImage ? 'active' : ''"
                    >
                      <img
                        src="img/products/jacket/lyle-scott-jacket-3.jpg"
                        alt=""
                      />
                    </div>

                    <div
                      class="pt"
                      @click="changeImage(thumbs[3])"
                      :class="thumbs[3] == mainImage ? 'active' : ''"
                    >
                      <img
                        src="img/products/jacket/lyle-scott-jacket-4.jpg"
                        alt=""
                      />
                    </div>
                  </carousel>
                </div>
              </div>
              <div class="col-lg-6">
                <div class="product-details text-left">
                  <div class="pd-title">
                    <span>{{productDetails.categories_id}}</span>
                    <h3>{{productDetails.name}}</h3>
                  </div>
                  <div class="pd-desc">
                    <p>{{productDetails.description}}</p>
                    <h4>${{productDetails.price}}</h4>
                  </div>
                  <div class="quantity">
                    <router-link to="/shopping-cart" class="primary-btn pd-cart"
                      >Add To Cart</router-link
                    >
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Product Shop Section End -->

    <RelatedProductsSection />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Header from "@/components/Header.vue";
import carousel from "vue-owl-carousel";
import RelatedProductsSection from "@/components/RelatedProductsSection.vue";
import Footer from "@/components/Footer.vue";

import axios from "axios";

export default {
  name: "Product",
  components: {
    // HelloWorld,
    Header,
    carousel,
    RelatedProductsSection,
    Footer,
  },
  data() {
    return {
      mainImage: "img/products/jacket/lyle-scott-jacket-1.jpg",
      thumbs: [
        "img/products/jacket/lyle-scott-jacket-1.jpg",
        "img/products/jacket/lyle-scott-jacket-2.jpg",
        "img/products/jacket/lyle-scott-jacket-3.jpg",
        "img/products/jacket/lyle-scott-jacket-4.jpg",
      ],
      productDetails: []
    };
  },
  methods: {
    changeImage(srcImage) {
      this.mainImage = srcImage;
    },
  },
  mounted() {
    axios
      .get("http://127.0.0.1:8000/api/product", {
        params: {
          id: this.$route.params.id
        }
      })
      .then((res) => (this.productDetails = res.data.data))
      // eslint-disable-next-line no-console
      .catch((err) => console.log(err));
  },
};
</script>

<style scoped>
.product-thumbs .pt {
  margin-right: 15px;
}
</style>