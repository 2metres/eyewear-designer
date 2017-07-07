<template>
  <div class="eyeglasses__root">
    <div class="eyeglasses__frame">
      <svg class="eyeglasses__lens" viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
        <rect
          id="lens1"
          v-bind:x="100 - lens.width.value - bridge.width.value"
          v-bind:y="100 - lens.height.value"
          v-bind:rx="lens.radius.value"
          v-bind:ry="lens.radius.value"
          v-bind:width="lens.width.value * 2"
          v-bind:height="lens.height.value * 2"
          v-bind:stroke-width="stroke.width.value"
          fill="none"
          stroke="black"
        />
        <line
          id="bridge"
          v-bind:x1="100 - bridge.width.value + lens.width.value"
          v-bind:y1="100 - bridge.height.value"
          v-bind:x2="200 + bridge.width.value - lens.width.value"
          v-bind:y2="100 - bridge.height.value"
          v-bind:stroke-width="stroke.width.value"
          fill="none"
          stroke="black"
        />
        <rect
          id="lens2"
          v-bind:x="200 - lens.width.value + bridge.width.value"
          v-bind:y="100 - lens.height.value"
          v-bind:rx="lens.radius.value"
          v-bind:ry="lens.radius.value"
          v-bind:width="lens.width.value * 2"
          v-bind:height="lens.height.value * 2"
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
      <vue-slider v-bind="lens.radius" v-model="lens.radius.value"></vue-slider>
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
      π: 3.141592653589793238462643383279,
      bridge: {
        width: {
          min: 0,
          max: 22,
          value: 10
        },
        height: {
          min: -18,
          max: 18,
          value: 0
        }
      },
      stroke: {
        width: {
          min: 1,
          max: 9,
          value: 3
        }
      },
      lens: {
        width: {
          min: 20,
          max: 52,
          value: 48
        },
        height: {
          min: 20,
          max: 52,
          value: 48
        },
        radius: {
          value: 50,
          max: 100,
          min: 0
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
