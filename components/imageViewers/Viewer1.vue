<template>
    <div class="img-wrapper h-3/4 mx-auto max-h-screen">
          <div class="relative">
            <img
            class="flex-shrink w-full border-gray-500"
            :src="`http://localhost:1337${featureImage}`"
            alt=""
            />
            <span v-if="offer" class="absolute top-4 left-4 bg-yellow-500 p-1 rounded">{{offer}}</span>
          </div>
          <div class="flex flex-row w-full justify-between">
            <img
            v-for="(url, i) in urls"
            class="w-1/5 p-1"
            :src="`http://localhost:1337${url}`"
            alt=""
            :class="[isCurrentImage(url) ? 'border-2 border-gray-500':'',]"
            @click="setCurrentImage(url)"
          />
          </div>
    </div>
</template>
<script>
export default {
    name: 'ImageViewer1',
    props: ['images', 'offer'],
    data(){
        const urls = this.images.map(image => image.attributes.url);
        const [featureImage, ...otherImages] = urls;
        return {
            featureImage,
            urls
        }
    },
    methods: {
        isCurrentImage(url){
            return url === this.featureImage
        },
        setCurrentImage(url){
            this.featureImage = url;
        }
    }
}
</script>
<style scoped>
    
</style>