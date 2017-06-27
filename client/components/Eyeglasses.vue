<template>
  <div class="eyeglasses__root">
    <div class="eyeglasses__frame">
      <svg class="eyeglasses__lens" viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
        <ellipse
          id="lens1"
          v-bind:cx="100 - bridgeWidth"
          v-bind:cy="100"
          v-bind:rx="valueX"
          v-bind:ry="valueY"
          v-bind:stroke-width="strokeWidth"
          fill="none"
          stroke="black"
        />
        <line
          id="bridge"
          v-bind:x1="100 - bridgeWidth + valueX"
          v-bind:x2="200 + bridgeWidth - valueX"
          v-bind:y1="100"
          v-bind:y2="100"
          v-bind:stroke-width="strokeWidth"
          fill="none"
          stroke="black"
        />
        <ellipse
          id="lens2"
          v-bind:cx="200 + bridgeWidth"
          v-bind:cy="100"
          v-bind:rx="valueX"
          v-bind:ry="valueY"
          v-bind:stroke-width="strokeWidth"
          fill="none"
          stroke="black"
        />
      </svg>
    </div>
    <div class="sliders">
      <vue-slider v-model="valueX"></vue-slider>
      <br>
      <br>
      <vue-slider v-model="valueY"></vue-slider>
      <br>
      <br>
      <vue-slider v-model="bridgeWidth"></vue-slider>
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
      bridgeWidth: 0,
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
