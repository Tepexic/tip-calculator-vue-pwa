<template>
  <div id="app" class="w-full h-screen flex items-center justify-center">
    <div class="max-w-sm px-4 text-purple-100 p-2">
      <div class="flex justify-center items-center">
        <svg class="w-12 mr-2 fill-current text-teal-500" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" focusable="false" viewBox="0 0 24 24"><path d="M9.33 11.5h2.17A4.5 4.5 0 0 1 16 16H8.999L9 17h8v-1a5.578 5.578 0 0 0-.886-3H19a5 5 0 0 1 4.516 2.851C21.151 18.972 17.322 21 13 21c-2.761 0-5.1-.59-7-1.625v-9.304A6.967 6.967 0 0 1 9.33 11.5zM5 19a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1v-9a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v9zM18 5a3 3 0 1 1 0 6a3 3 0 0 1 0-6zm-7-3a3 3 0 1 1 0 6a3 3 0 0 1 0-6z"/></svg>
        <h1 class="py-4 text-3xl font-bold text-center text-white"> Tip calculator </h1>
      </div>
      <!-- Total -->
      <div class="mt-10 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold">Check $</div>
        <input class="w-3/5 text-2xl focus:outline-none focus:bg-white focus:border-teal-500"
          v-model="check"
          @click="clearCheck"
          type="number"
          placeholder="Check total"/>
      </div>
      <!-- Tip % -->
      <div class="mt-10">
        <div class="flex justify-center items-center">
          <svg class="w-12 mr-2 fill-current text-green-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
          </svg>
          <Slider class="w-full"
            label="Tip %" min="0" max="30" :def="tip"
            v-on:new-value="getTip"/>
        </div>
      </div>
      <!-- Split check -->
      <div class="mt-6">
        <div class="flex justify-between items-center">
          <svg class="w-12 mr-2 fill-current text-yellow-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path d="M13 6a3 3 0 11-6 0 3 3 0 016 0zM18 8a2 2 0 11-4 0 2 2 0 014 0zM14 15a4 4 0 00-8 0v3h8v-3zM6 8a2 2 0 11-4 0 2 2 0 014 0zM16 18v-3a5.972 5.972 0 00-.75-2.906A3.005 3.005 0 0119 15v3h-3zM4.75 12.094A5.973 5.973 0 004 15v3H1v-3a3 3 0 013.75-2.906z" />
          </svg>
          <Slider class="w-full"
            label="Split check with" min="1" max="10" :def="people"
            v-on:new-value="getPeople"/>
        </div>
      </div>
      <!-- Results -->
      <div class="mt-8 flex justify-center items-center">
        <div class="mr-2 w-8/12 "></div>
        <div class="mr-2 mb-2 font-semibold text-xl w-4/12 text-center">Per person</div>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-6/12 text-right">Sub total</div>
        <div class="results w-6/12 text-xl focus:outline-none focus:bg-white focus:border-teal-500"
          id="subtotal"
          ref="subtotal">
          {{ subtotalDisplay }}
        </div>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-6/12 text-right">Tip </div>
        <div class="results w-6/12 text-xl focus:outline-none focus:bg-white focus:border-teal-500"
          id="tip"
          ref="tip">
          {{ tipPersonDisplay }}
        </div>
      </div>
      <div class="pb-4 flex justify-center items-center">
        <div class="mr-2 text-2xl font-semibold w-6/12 text-right">Total</div>
        <div class="results w-6/12 text-xl focus:outline-none focus:bg-white focus:border-teal-500"
          id="total"
          ref="total">
          {{ total }}
        </div>
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
  },

  data: function () {
    return {
      tip: 10,
      people: 1,
      check: 0,
    }
  },

  watch: {
    check: function () {
      this.save('check')
    }
  },

  computed: {
    subtotalDisplay: function () {
      return this.round(this.check / this.people, 2)
    },
    subtotal: function () {
      return this.check / this.people
    },
    tipPersonDisplay: function () {
      return this.round(this.tipPerson, 2)
    },
    tipPerson: function () {
      return (this.tip * (this.check / 100)) / this.people
    },
    total: function () {
      return this.round(this.subtotal + this.tipPerson, 2)
    }
  },

  methods: {
    round: function (n, decimals = 0) {
       return '$ ' + Number(`${Math.round(`${n}e${decimals}`)}e-${decimals}`).toString();
    },
    getTip: function (value) {
      this.tip = value
      this.save('tip')
    },
    getPeople: function (value) {
      this.people = value
      this.save('people')
    },
    save: function (p) {
      localStorage.setItem(p, JSON.stringify(this[p]))
    },
    clearCheck: function () {
      if(! this.check) this.check = null
    }
  },

  beforeMount: function () {
    this.check = JSON.parse(localStorage.getItem('check')) | 0
    this.tip = JSON.parse(localStorage.getItem('tip')) | 10
    this.people = JSON.parse(localStorage.getItem('people')) | 1
  },
}
//
</script>

<style>
@import './assets/styles.css';
</style>
