<template>
  <div class="eyeglasses__root">
    <div class="eyeglasses__frame">
      <svg class="eyeglasses__lens" viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
        <ellipse v-bind:cx="100" v-bind:cy="100" v-bind:rx="valueX" v-bind:ry="valueY" fill="transparent" stroke="black" v-bind:stroke-width="strokeWidth"/>
        <ellipse v-bind:cx="200" v-bind:cy="100" v-bind:rx="valueX" v-bind:ry="valueY" fill="transparent" stroke="black" v-bind:stroke-width="strokeWidth"/>
      </svg>
    </div>
    <div class="sliders">
      <vue-slider v-model="valueX"></vue-slider>
      <br>
      <br>
      <vue-slider v-model="valueY"></vue-slider>
      <br>
      <br>
      <vue-slider v-model="strokeWidth"></vue-slider>
    </div>
  </div>
</template>

<script>
import vueSlider from 'vue-slider-component';

export default {
  components: {
    vueSlider
  },
  data: function() {
		return {
      strokeWidth: 3,
			valueX: 30,
			valueY: 30
		}
	}
}
</script>

<style>
.sliders {
  background-color: white;
  position: fixed;
  bottom: 0;
  right: 0;
  left: 0;
  padding: 2em;
}
</style>
