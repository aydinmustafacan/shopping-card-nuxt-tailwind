<template>
  <section class="w-full text-center py-6 rounded-lg shadow-xl">
    <div class="bg-white max-w-xs shadow-lg   mx-auto border-b-4 border-indigo-500 rounded-2xl overflow-hidden  hover:shadow-2xl transition duration-500 transform hover:scale-105 cursor-pointer" >

      <div class="bg-blue-600 pt-1 px-2 bg-gradient-to-b from-indigo-100 to-indigo-200 rounded-xl shadow-lg w-52">
        <a href="/products" class="font-display max-w-sm text-2xl font-bold leading-tight">
          <span class="link link-underline link-underline-black text-black"> Shopping Cart by Mustafa using Nuxt & Tailwind</span>
        </a>
      </div>
    </div>

    <br/>

    <nuxt-link to="/products">
      <button class="border-2 rounded-full border-green-500 font-bold text-green-500 px-4 py-3 transition duration-300 ease-in-out hover:bg-green-500 hover:text-white mr-6">
        🛒
      </button>
    </nuxt-link>
  </section>
</template>


<style>
.link-underline {
  border-bottom-width: 0;
  background-image: linear-gradient(transparent, transparent), linear-gradient(#fff, #fff);
  background-size: 0 3px;
  background-position: 0 100%;
  background-repeat: no-repeat;
  transition: background-size .5s ease-in-out;
}

.link-underline-black {
  background-image: linear-gradient(transparent, transparent), linear-gradient(#E2C, #B2C)
}


.link-underline-purp {
  background-image: linear-gradient(transparent, transparent), linear-gradient(#F11, #F30)
}

.link-underline:hover {
  background-size: 100% 3px;
  background-position: 0 100%
}
</style>
