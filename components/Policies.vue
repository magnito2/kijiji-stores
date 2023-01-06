<template>
    <div class="policies flex my-4 mx-4 sm:px-4 justify-center">
        <transition name="fade">
            <div v-if="currPolicy == 0" class="policy shipping-policy justify-center mx-4 items-center">
                <div class="pr-4 pb-2 flex justify-center"><IconsVanIcon /></div>
                <div class="flex flex-col justify-center">
                    <h4 class="text-lg text-center">Free shipping and return</h4>
                    <p class="text-sm text-center">For all orders above 5000/=</p>
                </div>
        </div>
        </transition>
        <transition name="fade">
            <div v-if="currPolicy ==1" class="policy payment-policy flex mx-4 items-center">
                <div class="pr-4 pb-2"><IconsSuitecaseIcon /></div>
                <div class="flex flex-col">
                    <h4 class="text-lg text-center">Secure Payment</h4>
                    <p class="text-sm">We ensure secure payment</p>
                </div>
            </div>
        </transition>
        <transition name="fade">
            <div v-if="currPolicy ==2" class="policy money-back-policy flex mx-4 items-center">
                <div class="pr-4 pb-2"><IconsMoneyenvelopeIcon /></div>
                <div class="flex flex-col">
                    <h4 class="text-lg">Money back guarantee</h4>
                    <p class="text-sm">30 days money back</p>
                </div>
            </div>
        </transition>
        <transition name="fade">
            <div v-if="currPolicy ==3" class="policy shipping-policy flex mx-4 items-center">
                <div class="pr-4 pb-2"><IconsChatIcon /></div>
                <div class="flex flex-col">
                    <h4 class="text-lg">Customer support</h4>
                    <p class="text-sm">Call or email us 24/7</p>
                </div>
            </div>
        </transition>
    </div>
</template>
<script>
export default {
    name: 'Policies',
    data(){
        return {
            currPolicy: 0,
        }
    },
    methods: {
        changeCurrPolicy(){
            this.currPolicy = (this.currPolicy + 1) % 4
        }
    },
    watch: {
        currPolicy: {
            handler(value) {
                setTimeout(this.changeCurrPolicy, 5000);
            },
            immediate: true // This ensures the watcher is triggered upon creation
        }
    }

}
</script>
<style scoped>
.policy {
    @apply flex-col min-w-full
}
.fade-enter-active, .fade-leave-active {
  transition: opacity 1s;
}

.fade-enter-active {
    transition-delay: 1s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>