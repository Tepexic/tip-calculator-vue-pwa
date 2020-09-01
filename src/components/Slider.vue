<template>
<div class="flex justify-between items-center">
  <div class="mr-3 flex-1">
    <label class="font-semibold text-xl mb-4"> {{ label }} </label>
    <input class="slider w-full"
      type="range"
      :min="min"
      :max="max"
      @change="handleChange"
      v-model="rangeValue">
  </div>
  <input class="w-20 text-xl focus:outline-none focus:bg-white focus:border-teal-500"
    v-model="rangeValue"
    type="number"
    @keyup="handleChange"
    placeholder="0"/>
</div>
</template>

<script>
  export default {
    name: 'Slider',

    props: ['label', 'def', 'min', 'max'],

    data: function () {
      return {
        rangeValue: 0,
      }
    },

    mounted: function () {
      this.rangeValue = this.def
    },

    methods: { 
      handleChange: function () {
        if(this.rangeValue < this.min) {
          this.rangeValue = this.min
        }
        this.$emit('new-value', this.rangeValue)
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