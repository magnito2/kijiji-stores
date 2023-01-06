<template>
  <div
    class="hero relative h-64 flex flex-col justify-center text-center mx-auto"
  >
    <div class="absolute top-0 left-0">
        <img class="w-full max-h-64" src="~/assets/hero.png" alt="" />
    </div>
    <div class="relative">
      <div class="z-10 relative">
        <h1 class="text-3xl sm:text-5xl m-3 font-bold md:text-6xl">
          Home of African Fashion
        </h1>
        <p class="subtitle">...quality and affordable products</p>
      </div>
    </div>
    <div class="links absolute right-2 bottom-2">
        <NuxtLink to="/" class="button--hero relative z-10 text-md rounded flex  flex-row items-center px-3 py-2">
          <span>View Collections</span>
          <span><IconsArrowRightIcon /></span>
        </NuxtLink>
    </div>
    <div class="circle hidden sm:block sm:absolute z-0 right-16 top-16"></div>
  </div>
</template>

<script>
export default {
  name: "HeroSection",
};
</script>

<style scoped>
/* Sample `apply` at-rules with Tailwind CSS
  .container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
  }
  */
.hero {
  background-color: #F6F6F8;
  font-family: 'Inter', sans-serif;
}
.circle {
  width: 10em;
  height: 10em;
  border-radius: 5em;
  background: #b8738d;
}
.title {
  font-family: "Nunito";
  display: block;
  font-weight: 700;
  font-size: 50px;
  letter-spacing: 1px;
  line-height: 1em;
}
.subtitle {
  font-weight: 100;
  word-spacing: 2px;
}

.button--hero {
  background: #9A031E;
}
</style>
