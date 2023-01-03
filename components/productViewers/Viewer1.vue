<template>
    <div
        class="flex flex-col shadow-xl m-8 sm:m-2 md:m-4 justify-center items-center"
      >
        <ImageViewersViewer1 :images="product.attributes.Image.data"/>
        <div class="flex w-full flex-col">
          <h3 class="m-3 text-2xl">
            {{ product.attributes.name | capitalising }}
          </h3>
          <hr class="border-b-2 border-t-0 border-gray-300"/>
          <p class="product-price text-2xl m-3"><span class="pr-6 font-bold">4500/=</span><span class="line-through">6800/=</span></p>
          <p class="text-xl mx-3">Offer ends in : 122 Days, 14:58:32</p>
          <div class="rating flex items-center m-3">
            <span v-for="n in 5" class="pr-1"><IconsStarIcon /></span><span class="text-xl px-2">(5 Reviews)</span>
          </div>
          <div class="features">
            <ul class="mx-3">
              <li>Big area for your bumbum</li>
              <li>Chest thumb be a thing</li>
              <li>Shorter than your hankie</li>
            </ul>
          </div>
          <div class="size mx-3 my-3">
            <p class="text-sm">
              <span>Size:</span>
              <span class="border-2 border-gray-300 rounded p-0.5 m-0.5">Extra Large</span>
              <span class="border-2 border-gray-300 rounded p-0.5 m-0.5">Large</span>
              <span class="border-2 border-gray-300 rounded p-0.5 m-0.5">Medium</span>
              <span class="border-2 border-gray-300 rounded p-0.5 m-0.5">Small</span>
            </p>
          </div>
          <div class="flex mx-3">
            <div class="qty text-lg flex items-center border-2 border-gray-300 rounded-md">
              <span class="py-0.5 px-2 pr-6 mx-1">1</span>
              <span class="flex p-0.5 m-0.5 items-center">
                <span><IconsMinusCircleIcon /></span>
                <span><IconsPlusCircleIcon /></span>
              </span>
            </div>
            <div class="qty text-lg flex items-center border-2 border-gray-300 rounded-md mx-4">
              <span class="ml-2 mr-1"><IconsBasketIcon2 /></span>
              <span class="my-1 ml-1 mr-2">Add to Cart</span>
            </div>
          </div>
          <div class="flex mx-3 my-4">
            <div class="flex justify-evenly items-center mb-2">
              <span class="FACEBOOK-ICON mx-1">
                <IconsFacebookIcon />
              </span>
              <span class="TWITTER-ICON mx-1">
                <IconsTwitterIcon />
              </span>
              <span class="PINTREST-ICON mx-1">
                <IconsPintrestIcon />
              </span>
              <span class="TELEGRAM-ICON mx-1">
                <IconsTelegramIcon />
              </span>
            </div>
            <div class="border-r-2 mx-2 h-6 border-gray-300"></div>
            <div class="flex justify-evenly items-center mb-2">
              <span class="mx-1">
                <IconsHeartIcon />
              </span>
              <span class="mx-1">
                <IconsBalanceIcon />
              </span>
            </div>
          </div>
          <NuxtLink :to="`/products/${product.id}`" class="py-4 m-3">
            <button class="border-2 border-gray-200 p-2 rounded-md">View Product</button>
          </NuxtLink>
        </div>
      </div>
</template>
<script>
export default {
    name: 'ProductViewer1',
    props: ['product'],
    filters: {
      capitalising: function (data) {
        var capitalized = []
        data.split(' ').forEach(word => {
          capitalized.push(
            word.charAt(0).toUpperCase() +
            word.slice(1).toLowerCase()
          )
        })
        return capitalized.join(' ')
      }
    }
}
</script>
<style scoped>
    
</style>