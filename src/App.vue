<template>
  <div id="app" class="w-full h-screen container text-purple-100 p-2">
    <div class="h-full mx-auto max-w-sm px-4">
      <h1 class="py-4 text-3xl font-bold text-center "> Tip calculator </h1>
      <div class="pt-6 pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold">$</div>
        <input class="w-3/5 text-2xl focus:outline-none focus:bg-white focus:border-purple-500" type="number" placeholder="Check total"/>
      </div>
      <Slider />
      <Slider />
      <div class="mt-4 pb-2 flex justify-center items-center">
        <div class="mr-2 w-8/12 "></div>
        <div class="mr-2 text-xl w-4/12 text-center">Per person</div>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Sub total</div>
        <input class="w-4/12 text-xl focus:outline-none focus:bg-white focus:border-purple-500" type="number" placeholder="0"/>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Tip </div>
        <input class="w-4/12 text-xl focus:outline-none focus:bg-white focus:border-purple-500" type="number" placeholder="0"/>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Total</div>
        <input class="w-4/12 text-xl focus:outline-none focus:bg-white focus:border-purple-500" type="number" placeholder="0"/>
      </div>
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
  background: #41295a;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #2F0743, #41295a);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #2F0743, #41295a); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
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

/* Style */
input[type=number] {
  @apply font-semibold text-right appearance-none bg-gray-100 border-2 border-gray-200 rounded py-2 px-4 text-gray-800 leading-tight 
}
</style>
