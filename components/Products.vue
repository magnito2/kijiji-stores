<template>
  <div>
    <div
      class="sm:grid grid-cols-2 justify-center shadow-lg items-center gap-3 m-5 md:m-5"
    >
      <div>
        <img class="max-h-screen" :src="`http://localhost:1337${1}`" />
      </div>
      <div class="sm:m-3 md:m-5 p-3 sm:p-0">
        <p class="my-2"><span>Price: </span>{{ cartItem.price | formatPrice }}</p>
        <span class="my-2">Quantity: </span
        ><input
          v-model="cartItem.quantity"
          class="p-3 border border-solid border-t-0 border-l-0 border-r-0 border-b-1"
          type="number"
        />
        <p class="my-2 text-sm">{{ data.attributes.Description }}</p>
        <button
          class="button--green my-2"
          @click="
            addItemToCart(cartItem);
            displayMessage();
          "
        >
          Add to Cart
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "Products",
  props: ["data"],
  data() {
    return {
      cartItem: {
        id: this.data.id,
        name: this.data.attributes.name,
        url: `http://localhost:1337${1}`,
        price: this.data.attributes.Price,
        quantity: 1,
      },
    };
  },
  methods: {
    ...mapActions(["addItemToCart"]),
    displayMessage() {
      this.$swal({
        title: "Cart Updated!",
        text: `${this.cartItem.name} was added to your cart!`,
        icon: "success",
        button: "Ok",
      });
    },
  },
  filters: {
    formatPrice(price) {
      return `$${price}`;
    },
  },
};
</script>

<style scoped></style>
