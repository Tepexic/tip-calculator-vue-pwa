<template>
<div class="flex justify-between items-center">
  <div class="mr-3 flex-1">
    <label class="font-semibold text-xl mb-4"> {{ label }} </label>
    <input class="slider w-full" type="range" min="1" max="50" value="10">
  </div>
  <input class="w-20 text-xl focus:outline-none focus:bg-white focus:border-teal-500" type="number" placeholder="0"/>
</div>
</template>

<script>
  export default {
    props: {
      label: {
        type: String,
        required: true
      }
    }
  }
</script>

<style scoped>
/* The slider itself */
.slider {
    -webkit-appearance: none;  /* Override default CSS styles */
    appearance: none;
    height: 10px; /* Specified height */
    background: #ffffff;
    outline: none; /* Remove outline */
    opacity: 1; /* Set transparency (for mouse-over effects on hover) */
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
    background: #f5481d; 
    cursor: pointer; /* Cursor on hover */
}
.slider::-moz-range-thumb {
    width: 20px; /* Set a specific slider handle width */
    height: 20px; /* Slider handle height */
    background: #f5481d;
    cursor: pointer; /* Cursor on hover */
}

</style>