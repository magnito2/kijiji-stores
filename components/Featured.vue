<template>
  <div>
    <div class="flex flex-col justify-center items-center mx-4 border border-gray-300 p-1 rounded-xl">
      <div class="flex justify-between items-center w-full m-2">
        <h1 class="featured-header font-bold text-xl m-2">Featured Products</h1>
        <div class="text-xl font-bold">
          <span class="text-sm text-gray-500 font-light pr-2">{{ this.currIndex+1 }}/{{ this.fProducts.length }}</span>
          <span class="p-2" @click="decProduct" :class="{'text-gray-300' : isFirst}">&lt;</span>
          <span class="p-2" @click="incProduct" :class="{'text-gray-300' : isLast}">&gt;</span></div>
      </div>
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
  methods: {
    incProduct(){
      if(this.currIndex < this.fProducts.length-1){
        this.currIndex++;
      }
    },
    decProduct(){
      if(this.currIndex > 0){
        this.currIndex--;
      }
    }
  },
  computed: {
    currProduct(){
      return this.fProducts[this.currIndex];
    },
    isFirst(){
      return this.currIndex == 0;
    },
    isLast(){
      return this.currIndex == this.fProducts.length - 1;
    }
  }
};
</script>

<style scoped>
.featured-header {
  font-family: 'Comfortaa', cursive;
}
</style>
