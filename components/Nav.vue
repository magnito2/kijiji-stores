<template>
  <div
    class="flex items-center justify-between border-b z-50"
    :class="{ openMobileMenu: 'border-gray-400' }"
  >
    <nav class="w-full flex flex-col">
      <section class="MOBILE-MENU bg-gray-200 flex flex-col w-full lg:hidden pt-4 pb-2">
        <div
          class="MOBILE-MENU-BAR flex justify-between items-center py-2 w-full shadow-md"
        >
          <div class="HAMBURGER-ICON space-y-1.5 px-10" @click="toggleMobileMenu">
            <span
              class="block h-0.5 w-6 bg-gray-600"
              :class="[
                openMobileMenu
                  ? 'transform duration-200 translate-y-2.5 rotate-45'
                  : 'transform duration-200 rotate-0',
              ]"
            ></span>
            <span
              class="block h-0.5 w-6 bg-gray-600"
              :class="[
                openMobileMenu
                  ? 'transform duration-500 -translate-x-full opacity-0 ease-in-out'
                  : 'transform duration-500 translate-x-0',
              ]"
            ></span>
            <span
              class="block h-0.5 w-6 bg-gray-600"
              :class="[
                openMobileMenu
                  ? 'transform duration-200 -translate-y-2.5 -rotate-45 '
                  : 'transform duration-200 rotate-0',
              ]"
            ></span>
          </div>
          <div class="LOGO w-32 px-4"><img src="~/assets/logo.png" alt="" /></div>
          <div class="CART-ICON px-10">
            <IconsBasketIcon />
          </div>
        </div>
        <div
          class="NAVIGATION-MOBILE-OPEN w-full bg-gray-200 absolute shadow-md"
          :class="[
            openMobileMenu
              ? 'top-16 transform duration-500 ease-in-out'
              : '-top-72 transform duration-500 ease-in-out opacity-0',
          ]"
          @click="toggleMobileMenu"
        >
          <ul class="flex flex-col items-center justify-between">
            <li class="border-b border-gray-400 my-8 uppercase">
              <a href="/about">About</a>
            </li>
            <li class="border-b border-gray-400 my-8 uppercase">
              <a href="/portfolio">Portfolio</a>
            </li>
            <li class="border-b border-gray-400 my-8 uppercase">
              <a href="/contact">Contact</a>
            </li>
          </ul>
        </div>
      </section>

      <section class="DESKTOP-MENU hidden sm:flex justify-between items-center px-8 py-2">
        <div class="LOGO w-32"><img src="~/assets/logo.png" alt="" /></div>
        <div class="SEARCH border-2 p-1 rounded-md">
          <form action="" class="flex divide-x-2 items-center">
            <fieldset class="px-2">
              <select name="categories" id="categories">
              <option value="All Categories">All Categories</option>
              <option value="Dresses">Dresses</option>
              <option value="Shirts">Shirts</option>
              <option value="Hats">Hats</option>
              <option value="Shoes">Shoes</option>
              <option value="Belts">Belts</option>
            </select>
            </fieldset>
            <fieldset class="px-2 flex items-center">
              <input type="text" placeholder="Search in ..." class="">
            <button type="submit" class="">
              <span class="ICON flex wrap">
                <IconsLensIcon />
              </span>
            </button>
            </fieldset>
          </form>
        </div>
        <ul class="space-x-8 flex">
        <li>
          <a href="/wishlist" class="flex flex-col justify-center items-center">
            <IconsHeartIcon />
            <span>Wishlist</span>
          </a>
        </li>
        <li>
          <a href="/compare"  class="flex flex-col justify-center items-center">
            <IconsBalanceIcon />
            <span>Compare</span>
          </a>
        </li>
        <li>
          <a href="/cart"  class="flex flex-col justify-center items-center">
            <IconsBasketIcon />
            <span>Cart</span>
          </a>
        </li>
      </ul>
      </section>
    </nav>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "Nav",
  data() {
    return { openMobileMenu: false };
  },
  computed: {
    ...mapGetters(["getCart"]),
  },
  methods: {
    toggleMobileMenu() {
      this.openMobileMenu = !this.openMobileMenu;
    },
  },
};
</script>

<style scoped>
.ham-menu {
  background-color: #000;
  width: 3em;
  height: 3em;
  border-radius: 1.5em;
}
.cart {
  background-color: rgb(163, 87, 129);
  width: 3em;
  height: 3em;
  border-radius: 1.5em;
}
.navbar {
  background-color: rgb(24, 20, 22);
}
.cartCount {
  background: #000;
  border-radius: 30%;
}
.SEARCH {
  border-color: #9A031E;
}

.DESKTOP-MENU {
  background-color: #fff;
}

input:focus, textarea:focus, select:focus{
        outline: none;
}
</style>
