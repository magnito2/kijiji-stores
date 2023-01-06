<template>
  <div>
    <div class="flex justify-center items-center">
        <ProductViewersViewer1 :product="currProduct" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Featured",
  props: ["fProducts"],
  data(){
    return {
      currIndex: 0,
    }
  },
  computed: {
    currProduct(){
      return this.fProducts[this.currIndex];
    }
  }
};
</script>

<style scoped></style>
