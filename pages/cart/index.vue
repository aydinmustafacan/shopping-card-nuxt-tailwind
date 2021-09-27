<template>
    <div class="sidenav flex content-between flex-wrap">
        <div class="container">
            <Cart v-for="product in products" :key="product.id" :product="product" />
        </div>
        <div class="container">
            <p class="text-lg my-2">Total amount: <span class="text-blue-600">{{ totalAmount }} $</span></p>
          <div class="bg-white max-w-xs shadow-lg   mx-auto border-b-4 border-indigo-500 rounded-2xl overflow-hidden  hover:shadow-2xl transition duration-500 transform hover:scale-105 cursor-pointer" >

          <button class="w-full bg-red-400 hover:bg-red-600 text-white font-bold py-2 rounded">Checkout</button>
            </div>
        </div>
    </div>
</template>

<script>
import Cart from './cart'

export default {
    layout: ({ isMobile }) => isMobile ? 'mobile' : 'default',
    components: { Cart },
    computed: {
        products() {
            return this.$store.getters['cart/cart']
        },
        totalAmount() {
            return this.$store.getters['cart/totalAmount']
        }
    }
}
</script>
