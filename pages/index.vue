<template>
  <div>
    <Nav class="sticky top-0" />
    <HeroSection />
    <Policies />
    <div class="sm:w-11/12 md:w-4/5 mx-auto">
      <Featured class="mx-auto" :fProducts="featuredProducts" />
    </div>
    <Ads class="mx-auto sm:m-10" />
    <NewsLetter class="mx-auto" />
    <Footer />
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  async asyncData({ $strapi, store, error }) {
    try {
      const response = await $strapi.$products.find({
        //featured: true,
        populate: "*",
      });

      console.log(response);
      store.commit("setFeaturedProducts", response.data);
    } catch (e) {
      error(e);
    }
  },
  data() {
    return {
      featuredProds: [],
    };
  },
  computed: {
    ...mapGetters(["featuredProducts"]),
  },
};
</script>

<style scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
