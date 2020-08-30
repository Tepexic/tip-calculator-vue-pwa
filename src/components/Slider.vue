<template>
  <div class="py-4">
    <div class="flex justify-center items-center">
      <svg class="w-12 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
        <path fill-rule="evenodd" d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
      </svg>
      <div class="mr-2">
        <label class="font-semibold text-xl mb-2"> Tip % </label>
        <input class="slider w-full" type="range" min="1" max="50" value="10">
      </div>
      <input class="w-20 px-3 py-2 rounded text-right text-xl shadow appearance-none border text-gray-700 leading-tight focus:outline-none focus:shadow-outline font-semibold" type="number" placeholder="0"/>
      <div class="ml-2 text-2xl font-semibold">%</div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
/* The slider itself */
.slider {
    -webkit-appearance: none;  /* Override default CSS styles */
    appearance: none;
    height: 10px; /* Specified height */
    background: #d3d3d3; /* Grey background */
    outline: none; /* Remove outline */
    opacity: 01; /* Set transparency (for mouse-over effects on hover) */
    -webkit-transition: .2s; /* 0.2 seconds transition on hover */
    transition: opacity .2s;
}
/* Mouse-over effects */
.slider:hover {
    opacity: 1; /* Fully shown on mouse-over */
}
/* The slider handle (use -webkit- (Chrome, Opera, Safari, Edge) and -moz- (Firefox) to override default look) */
.slider::-webkit-slider-thumb {
    -webkit-appearance: none; /* Override default look */
    appearance: none;
    width: 20px; /* Set a specific slider handle width */
    height: 20px; /* Slider handle height */
    background: #f59b25; 
    cursor: pointer; /* Cursor on hover */
}
.slider::-moz-range-thumb {
    width: 12px; /* Set a specific slider handle width */
    height: 12px; /* Slider handle height */
    background: #f59b25;
    cursor: pointer; /* Cursor on hover */
}

</style>