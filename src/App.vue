<template>
  <div id="app" class="w-full h-screen container bg-cover text-white p-2">
    <div class="h-full mx-auto max-w-sm px-4 bg-purple-900 bg-opacity-50 rounded">
      <h1 class="py-4 text-3xl font-bold text-center "> Tip calculator </h1>
      <div class="pt-6 pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold">$</div>
        <input class="w-40 px-3 py-2 rounded text-right text-xl shadow appearance-none border text-purple-900 leading-tight focus:outline-none focus:shadow-outline font-semibold" type="number" placeholder="Check total"/>
      </div>
      <Slider />
      <Slider />
      <div class="pb-2 flex justify-center items-center">
        <div class="mr-2 w-8/12 "></div>
        <div class="mr-2 text-xl w-4/12 text-center">Per person</div>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Sub total</div>
        <input class="w-4/12 px-3 py-2 rounded text-right text-xl shadow appearance-none border text-purple-900 leading-tight focus:outline-none focus:shadow-outline font-semibold" type="number" placeholder="0"/>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Tip </div>
        <input class="w-4/12 px-3 py-2 rounded text-right text-xl shadow appearance-none border text-purple-900 leading-tight focus:outline-none focus:shadow-outline font-semibold" type="number" placeholder="0"/>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Total</div>
        <input class="w-4/12 px-3 py-2 rounded text-right text-xl shadow appearance-none border text-purple-900 leading-tight focus:outline-none focus:shadow-outline font-semibold" type="number" placeholder="0"/>
      </div>
      <div class="text-center px-2 mt-4 mb-2 text-xs uppercase">Photo by <a href="https://unsplash.com/@dosejuice?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Dose Juice</a> on <a href="https://unsplash.com/?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></div>
    </div>
  </div>
</template>

<script>
import Slider from '@/components/Slider'
export default {
  name: 'App',
  components: {
    Slider
  }
}
//
</script>

<style>
@import './assets/styles.css';
#app {
  background-image: url(./assets/bg.jpg);
}

/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type=number] {
  -moz-appearance: textfield;
}
</style>
