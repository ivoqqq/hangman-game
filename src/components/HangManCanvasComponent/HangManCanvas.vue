<template>
  <canvas id="canvas" width="200" height="200" style="border: 2px solid white"
    >Your browser does not support the HTML canvas tag.</canvas
  >
</template>

<script>
import { coordinates } from "./canvas-coordinates.js";

export default {
  props: {
    mistakesLeft: {
      type: Number,
      validator: function (value) {
        return [11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0].indexOf(value) !== -1;
      },
    },
  },
  methods: {
    draw: function (array) {
      var [x, y, tX, tY, width, cX, cY, r] = array;
      var c = document.getElementById("canvas");
      var ctx = c.getContext("2d");
      ctx.beginPath();
      ctx.strokeStyle = "crimson";
      ctx.lineWidth = width;

      if (Object.values(coordinates)[3]) {
        ctx.arc(cX, cY, r, 0, 2 * Math.PI);
        ctx.fillStyle = "crimson";
        ctx.fill();
      }
      ctx.moveTo(x, y);
      ctx.lineTo(tX, tY);
      ctx.stroke();
    },
  },
  watch: {
    mistakesLeft() {
      var hangElements = Object.values(coordinates);
      for (let index = 0; index < hangElements.length; index++) {
        if (index === 8 - this.mistakesLeft) {
          this.draw(hangElements[index]);
        }
      }
    },
  },
};
</script>

<style scoped>
#canvas {
  display: block;
  position: relative;
  top: calc(50% - 100px);
  left: calc(50% - 102px);
}
</style>