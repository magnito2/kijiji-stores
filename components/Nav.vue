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
          <div class="HAMBURGER-ICON space-y-2 px-10" @click="toggleMobileMenu">
            <span
              class="block h-0.5 w-8 bg-gray-600"
              :class="[
                openMobileMenu
                  ? 'transform duration-200 translate-y-2.5 rotate-45'
                  : 'transform duration-200 rotate-0',
              ]"
            ></span>
            <span
              class="block h-0.5 w-8 bg-gray-600"
              :class="[
                openMobileMenu
                  ? 'transform duration-500 -translate-x-full opacity-0 ease-in-out'
                  : 'transform duration-500 translate-x-0',
              ]"
            ></span>
            <span
              class="block h-0.5 w-8 bg-gray-600"
              :class="[
                openMobileMenu
                  ? 'transform duration-200 -translate-y-2.5 -rotate-45 '
                  : 'transform duration-200 rotate-0',
              ]"
            ></span>
          </div>
          <div class="LOGO w-32 px-4"><img src="~/assets/logo.png" alt="" /></div>
          <div class="CART-ICON px-10">
            <svg
              width="22"
              height="29"
              viewBox="0 0 22 29"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M2.44444 28.5H19.5556C20.9037 28.5 22 27.2442 22 25.7V10.3C22 9.9287 21.8712 9.5726 21.642 9.31005C21.4128 9.0475 21.1019 8.9 20.7778 8.9H17.1111V7.5C17.1111 3.6402 14.3697 0.5 11 0.5C7.63033 0.5 4.88889 3.6402 4.88889 7.5V8.9H1.22222C0.898069 8.9 0.587192 9.0475 0.357981 9.31005C0.128769 9.5726 0 9.9287 0 10.3V25.7C0 27.2442 1.09633 28.5 2.44444 28.5ZM7.33333 7.5C7.33333 5.1844 8.97844 3.3 11 3.3C13.0216 3.3 14.6667 5.1844 14.6667 7.5V8.9H7.33333V7.5ZM2.44444 11.7H4.88889V14.5H7.33333V11.7H14.6667V14.5H17.1111V11.7H19.5556L19.558 25.7H2.44444V11.7Z"
                fill="black"
              />
            </svg>
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

      <ul class="DESKTOP-MENU hidden space-x-8 sm:flex">
        <li>
          <a href="/about">About</a>
        </li>
        <li>
          <a href="/portfolio">Portfolio</a>
        </li>
        <li>
          <a href="/contact">Contact</a>
        </li>
      </ul>
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
</style>
