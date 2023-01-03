<template>
  <div
    class="footer flex flex-col mt-10 sm:mt-0 sm:flex-row sm:mx-20 sm:justify-between space-x-5 p-5 py-8 md:space-x-20 md:p-20 text-sm"
  >
    <div class="flex flex-col">
      <img class="w-32 mb-2" src="~/assets/logo.png" alt="logo" />
      <p class="mb-1">Got questions? call 24/7</p>
      <p class="mb-1">+254-7-545-000</p>
      <p class="mb-1">Register to get coupons</p>
      <div class="flex justify-evenly items-center mb-2">
        <span class="FACEBOOK-ICON"
          ><IconsFacebookIcon /></span
        ><span class="TWITTER-ICON"
          ><IconsTwitterIcon /></span
        ><span class="PINTREST-ICON"
          ><IconsPintrestIcon /></span
        ><span class="TELEGRAM-ICON"
          ><IconsTelegramIcon />
        </span>
      </div>
    </div>
    <div class="flex flex-col">
      <h3 class="text-lg">COMPANY</h3>
      <p class="text-sm">About us</p>
      <p class="text-sm">Team members</p>
      <p class="text-sm">Order History</p>
    </div>
    <div class="flex flex-col">
      <h3 class="text-lg">MY ACCOUNT</h3>
      <p class="text-sm">Track order</p>
      <p class="text-sm">View Cart</p>
      <p class="text-sm">My Wishlist</p>
      <p class="text-sm">Sign in</p>
      <p class="text-sm">Privacy policy</p>
    </div>
    <div class="flex flex-col">
      <h3 class="text-lg">CUSTOMER SERVICE</h3>
      <p class="text-sm">Payment methods</p>
      <p class="text-sm">Money back guarantee</p>
      <p class="text-sm">Product returns</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.footer {
  background: #d9d9d9;
}
</style>
