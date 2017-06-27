<template>
  <div class="eyeglasses__root">
    <div class="eyeglasses__frame">
      <svg class="eyeglasses__lens" viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
        <ellipse
          id="lens1"
          v-bind:cx="100 - bridge.width.value"
          v-bind:cy="100"
          v-bind:rx="lens.width.value"
          v-bind:ry="lens.height.value"
          v-bind:stroke-width="stroke.width.value"
          fill="none"
          stroke="black"
        />
        <line
          id="bridge"
          v-bind:x1="100 - bridge.width.value + lens.width.value - bridge.height.value / π"
          v-bind:x2="200 + bridge.width.value - lens.width.value + bridge.height.value / π"
          v-bind:y1="100 - bridge.height.value"
          v-bind:y2="100 - bridge.height.value"
          v-bind:stroke-width="stroke.width.value"
          fill="none"
          stroke="black"
        />
        <ellipse
          id="lens2"
          v-bind:cx="200 + bridge.width.value"
          v-bind:cy="100"
          v-bind:rx="lens.width.value"
          v-bind:ry="lens.height.value"
          v-bind:stroke-width="stroke.width.value"
          fill="none"
          stroke="black"
        />
      </svg>
    </div>
    <div class="sliders">
      <vue-slider v-bind="lens.width" v-model="lens.width.value"></vue-slider>
      <br>
      <br>
      <vue-slider v-bind="lens.height" v-model="lens.height.value"></vue-slider>
      <br>
      <br>
      <vue-slider v-bind="bridge.width" v-model="bridge.width.value"></vue-slider>
      <br>
      <br>
      <vue-slider v-bind="bridge.height" v-model="bridge.height.value"></vue-slider>
      <br>
      <br>
      <vue-slider v-bind="stroke.width" v-model="stroke.width.value"></vue-slider>
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
      π: 3.141592653589793238462643383279502884197169399375105820974944592307816406286,
      bridge: {
        width: {
          min: -19,
          max: 19,
          value: 12
        },
        height: {
          min: -18,
          max: 18,
          value: 0
        }
      },
      stroke: {
        width: {
          min: 3,
          max: 15,
          value: 3
        }
      },
      lens: {
        width: {
          min: 20,
          max: 64,
          value: 48
        },
        height: {
          min: 20,
          max: 64,
          value: 48
        }
      }
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
