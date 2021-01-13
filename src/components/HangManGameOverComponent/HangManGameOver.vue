<template>
  <div class="gameOverModal" v-if="gameOver">
    <div class="gameOverMessage">
      <div class="winner" v-if="checkWinner">
        Congrats! You solved the word!
      </div>
      <div class="winner" v-if="checkLoser">Sorry! You didn't make it!</div>
      <button @click="restart">Play Again</button>
    </div>
  </div>
</template>

<script>
import { words } from "../hangman-words.js";
export default {
  props: {
    gameOver: {
      type: Boolean,
    },
    checkWinner: {
      type: Boolean,
    },
    checkLoser: {
      type: Boolean,
    },
  },
  methods: {
    restart: function () {
      var canvas = document.getElementById("canvas");
      var ctx = canvas.getContext("2d");
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      this.$parent.$refs.letter.forEach((l) =>
        l.setAttribute("style", "color: white; background: transparent")
      );
      this.$parent.$el.querySelector(".wrap").style.removeProperty("filter");
      Object.assign(this.$parent.$data, this.$parent.$options.data.apply(this));
      this.$parent.range = Array(90 - 65 + 1)
        .fill()
        .map((el, i) => 65 + i);
      // create an array of range for v-for uppercase from A to Z
      this.$parent.categories = Object.keys(words);
    },
  },
};
</script>

<style scoped>
.gameOverModal {
  position: fixed;
  background-color: rgba(0, 0, 2, 0.5);
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 10;
  animation-name: fadeIn;
  animation-duration: 0.5s;
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.gameOverMessage {
  height: 100px;
  width: 300px;
  position: absolute;
  top: 60%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
}
@media only screen and (max-height: 1000px) {
  .gameOverMessage {
    top: 70%;
  }
}
.gameOverMessage button {
  position: absolute;
  background: crimson;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  outline: none;
}
.winner {
  padding-top: 10px;
  text-align: center;
  margin: auto;
  left: 0;
  right: 0;
  background: darkslategray;
}
</style>