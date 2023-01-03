<template>
  <div>
    <div class="sm:grid sm:grid-cols-3 md:grid-cols-3 gap-6 justify-center items-center">
      <template v-for="(product, i) in fProducts">
        <ProductViewersViewer1 :product="product" />
      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: "Featured",
  props: ["fProducts"],
};
</script>

<style scoped></style>
