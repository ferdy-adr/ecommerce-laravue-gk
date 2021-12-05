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
                    <span>oranges</span>
                    <h3>Pure Pineapple</h3>
                  </div>
                  <div class="pd-desc">
                    <p>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                      Corporis, error officia. Rem aperiam laborum voluptatum
                      vel, pariatur modi hic provident eum iure natus quos non a
                      sequi, id accusantium! Autem.
                    </p>
                    <p>
                      Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                      Quam possimus quisquam animi, commodi, nihil voluptate
                      nostrum neque architecto illo officiis doloremque et
                      corrupti cupiditate voluptatibus error illum. Commodi
                      expedita animi nulla aspernatur. Id asperiores blanditiis,
                      omnis repudiandae iste inventore cum, quam sint molestiae
                      accusamus voluptates ex tempora illum sit perspiciatis.
                      Nostrum dolor tenetur amet, illo natus magni veniam quia
                      sit nihil dolores. Commodi ratione distinctio harum
                      voluptatum velit facilis voluptas animi non laudantium, id
                      dolorem atque perferendis enim ducimus? A exercitationem
                      recusandae aliquam quod. Itaque inventore obcaecati, unde
                      quam impedit praesentium veritatis quis beatae ea atque
                      perferendis voluptates velit architecto?
                    </p>
                    <h4>$495.00</h4>
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
    };
  },
  methods: {
    changeImage(srcImage) {
      this.mainImage = srcImage;
    },
  },
};
</script>

<style scoped>
.product-thumbs .pt {
  margin-right: 15px;
}
</style>