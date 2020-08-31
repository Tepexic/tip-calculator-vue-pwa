<template>
  <div id="app" class="w-full h-screen">
    <div class="h-full mx-auto max-w-sm px-4 text-purple-100 p-2">
      <div class="flex justify-center items-center">
        <svg class="w-12 mr-2 fill-current text-teal-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd" d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
        </svg>
        <h1 class="py-4 text-3xl font-bold text-center text-white"> Tip calculator </h1>
      </div>
      <!-- Total -->
      <div class="mt-10 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold">$</div>
        <input class="w-3/5 text-2xl focus:outline-none focus:bg-white focus:border-teal-500" type="number" placeholder="Check total"/>
      </div>
      <!-- Tip % -->
      <div class="mt-10">
        <div class="flex justify-center items-center">
          <svg class="w-12 mr-2 fill-current text-green-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
          </svg>
          <Slider class="w-full" label="Tip %"/>
        </div>
      </div>
      <!-- Split check -->
      <div class="mt-6">
        <div class="flex justify-between items-center">
          <svg class="w-12 mr-2 fill-current text-yellow-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path d="M13 6a3 3 0 11-6 0 3 3 0 016 0zM18 8a2 2 0 11-4 0 2 2 0 014 0zM14 15a4 4 0 00-8 0v3h8v-3zM6 8a2 2 0 11-4 0 2 2 0 014 0zM16 18v-3a5.972 5.972 0 00-.75-2.906A3.005 3.005 0 0119 15v3h-3zM4.75 12.094A5.973 5.973 0 004 15v3H1v-3a3 3 0 013.75-2.906z" />
          </svg>
          <Slider class="w-full" label="Split check with"/>
        </div>
      </div>
      <!-- Results -->
      <div class="mt-8 flex justify-center items-center">
        <div class="mr-2 w-8/12 "></div>
        <div class="mr-2 mb-2 text-xl w-4/12 text-center">Per person</div>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Sub total</div>
        <input class="w-4/12 text-xl focus:outline-none focus:bg-white focus:border-teal-500" type="number" placeholder="0"/>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Tip </div>
        <input class="w-4/12 text-xl focus:outline-none focus:bg-white focus:border-teal-500" type="number" placeholder="0"/>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-8/12 text-right">Total</div>
        <input class="w-4/12 text-xl focus:outline-none focus:bg-white focus:border-teal-500" type="number" placeholder="0"/>
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
</style>
