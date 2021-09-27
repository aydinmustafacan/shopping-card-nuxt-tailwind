<template>
    <div class="container max-w-sm w-full flex mb-4">

        <div class="flex flex-col justify-between ml-4 w-1/2">

          <div class="bg-white max-w-xs shadow-lg   mx-auto border-b-4 border-green-500 rounded-2xl overflow-hidden  hover:shadow-2xl transition duration-500 transform hover:scale-105 cursor-pointer" >

            <p class="text-gray-900 font-bold text-2xl"><a class="border-2 rounded-full border-green-500 font-bold text-green-500 px-4 py-3 transition duration-300 ease-in-out hover:bg-green-500 hover:text-white mr-6">
              🛒
            </a>  {{ product.productName }}</p>
                <p class="text-blue-600">{{ product.price.toFixed(2) }}$</p>
            </div>
            <div class="inline-flex">
                <button class="bg-red-400 hover:bg-red-600 text-white font-semibold py-2 px-4 rounded-l" @click="removeFromCart">-</button>
                <span class="bg-red-400 py-2 px-4 text-white">{{ product.quantity || '0' }}</span>
                <button class="bg-red-400 hover:bg-red-600 text-white font-semibold py-2 px-4 rounded-r" @click="addToCart">+</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['product'],
    methods: {
        removeFromCart() {
            this.$store.dispatch('cart/removeFromCart', this.product).then(() => {
                this.$store.dispatch('products/addToStock', this.product)
            }).catch(err => console.log(err))
        },
        addToCart() {
            this.$store.dispatch('cart/addToCart', this.product).then(() => {
                this.$store.dispatch('products/takeFromStock', this.product)
            }).catch(err => console.log(err))
        }
    }
}
</script>
