<template>
  <div class="container">
    <hint-component
      @showHint="showHint = $event"
      @addMistakes="addMistakes = $event"
      :show-hint="showHint"
      :word="word"
      :word-hint="wordHint"
      :count-letter="countLetter"
    ></hint-component>
    <game-over-component   
      :check-winner="checkWinner"
      :check-loser="checkLoser"
      :game-over="gameOver"
    ></game-over-component>
    <!-- Main -->
    <div class="wrap">
      <button class="fullScreen" @click="chromeFullScreen">
        Go Full Screen
      </button>
      <div class="columns">
        <div class="hint">
          <button @click="openHintModal" :disabled="!disabled">Hint</button>
        </div>
        <div class="select-wrapper">
          <select v-model="selected" :disabled="disabled">
            <option disabled hidden value="">Please select category</option>
            <option
              class="category"
              v-for="category in categories"
              :key="category"
            >
              {{ category }}
            </option>
          </select>
        </div>
        <div class="mistakes">Mistakes left: {{ mistakesLeft }}</div>
      </div>
      <div class="dashed">
        <div>{{ dashes }}</div>
        <!-- <div v-for="(ch, index) in countLetter" :key="'ch' + index">{{ ch }}</div> -->
      </div>
      <canvas-component :mistakes-left="mistakesLeft"></canvas-component>
      <div class="keyboard">
        <span
          ref="letter"
          class="key active"
          v-for="char in range"
          :key="char"
          >{{ String.fromCharCode(char) }}</span
        >
        <!-- като форматирам и ми слага space преди и след буквата??? -->
      </div>
    </div>
  </div>
</template>

<script>
// import ModalHintContainer from './ModalHintContainer.vue';
import { words } from "./hangman-words.js";
import CanvasComponent from "./HangManCanvasComponent/HangManCanvas.vue";
import GameOverComponent from "./HangManGameOverComponent/HangManGameOver.vue";
import HintComponent from "./HangManHintComponent/HangManHintComponent.vue";
export default {
  // components: { ModalHintContainer },
  components: { CanvasComponent, GameOverComponent, HintComponent },
  data() {
    return {
      range: null,
      disabled: false,
      selected: "",
      categories: null,
      index: null,
      showHint: false,
      countLetter: [],
      checkWinner: false,
      checkLoser: false,
      gameOver: false,
      wrongKeys: [],
      char: null,
      addMistakes: 0,
      word: null,
      wordHint: null
      // hintsLeft: 2,
    };
  },

  created: function () {
    this.range = Array(90 - 65 + 1)
      .fill()
      .map((el, i) => 65 + i); //create an array of range for v-for uppercase from A to Z
    this.categories = Object.keys(words); //create an array of categories for v-for select option
  },
  computed: {
    dashes: function () {
      return this.countLetter.join(" "); //join the output to display it without []...
    },
    // joker: function () {
    //   return words[this.selected][this.index].hint.toUpperCase();
    // },
    mistakesLeft: function () {
      return 9 + this.addMistakes - [...new Set(this.wrongKeys)].length;
    },
  },
  methods: {
    openHintModal: function () {
      this.showHint = !this.showHint;
      this.$el
        .querySelector(".wrap")
        .setAttribute("style", "filter: blur(1px)");
    },

    keyPressed: function () {
      //mouse click or keyboard button press
      // console.log(event)
      if (event.type === "click") {
        this.char = event.target.innerHTML.toUpperCase(); //ensure upper and lower case letters =>> capsLock on/off
      } else {
        this.char = event.key.toUpperCase(); //ensure upper and lower case letters =>> capsLock on/off
      }
      for (var i = 0; i < words[this.selected][this.index].word.length; i++) {
        if (this.char === words[this.selected][this.index].word[i]) {
          this.countLetter.splice(i, 1, this.char); //replace "_" with letter
        }
      }
      /* change the color of pressed letter */
      for (var j = 0; j < this.$refs.letter.length; j++) {
        if (this.char === this.$refs.letter[j].innerHTML) {
          if (words[this.selected][this.index].word.includes(this.char)) {
            // this.char.setAttribute("style","color: black; background: white");
            this.$refs.letter[j].setAttribute(
              "style",
              "color: black; background: white"
            );
          } else {
            this.$refs.letter[j].setAttribute("style", "background: crimson");
            this.wrongKeys.push(this.char);
          }
        }
      }
    },
    removeListenerEndGame() {
      this.gameOver = true;
      document
        .querySelector(".wrap")
        .setAttribute("style", "filter: blur(1px)");
      window.removeEventListener("keyup", this.keyPressed);
      window.removeEventListener("click", this.keyPressed);
    },
    chromeFullScreen: function () {
      document.documentElement.webkitRequestFullScreen();
    },
  },
  watch: {
    countLetter: function () {
      if (!this.countLetter.includes("_") && this.countLetter.length > 0) {
        this.checkWinner = true;
        this.removeListenerEndGame();
      }
    },
    mistakesLeft: function () {
      if (this.mistakesLeft === 0) {
        this.checkLoser = true;
        this.removeListenerEndGame();
      }
    },
    selected: function () {
      // TODO - да го направя на метод он клик

      //random generated word from the chosen category
      //this.words[this.selected] => ArrayFrom words and hints in the chosen category
      //this.selected => selectedCategory
      if (this.selected !== "") {
        this.index = Math.floor(Math.random(1) * words[this.selected].length);
        this.countLetter = Array(
          words[this.selected][this.index].word.length
        ).fill("_");
        this.word = words[this.selected][this.index].word;
        this.wordHint = words[this.selected][this.index].hint.toUpperCase();
        this.disabled = !this.disabled;
        window.addEventListener("keyup", this.keyPressed);
        window.addEventListener("click", this.keyPressed);
      }
    },
    hintsLeft: function () {
      console.log(this.hintsLeft);
      //TODO: disable hint button when hint is used two times
    },
  }
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  /* user-select: none; */
  /* box-sizing: border-box; */
}
.container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  color: white;
  display: table;
  background: rgb(32, 54, 54);
}

.fullScreen {
  position: absolute;
  top: 120px;
  left: 20px;
  color: white;
  height: 30px;
  width: 120px;
  border: 2px solid white;
  outline: none;
  cursor: pointer;
  z-index: 20;
}

/* .closeBtn:before {
  content: "";
  width: 50px;
  height: 50px;
  background: black;
} */
/* @media only screen and (max-width: 600px) {
  #wheel {
    width: 250px;
    height: 250px;
  }
} */

.wrap {
  display: table-cell;
  vertical-align: middle;
}
.columns {
  display: flex; /* establish flex container */
  justify-content: center; /* switched from default (flex-start, see below) */
}

.hint,
.select-wrapper,
.mistakes {
  width: 50px;
  margin-bottom: 10px;
  position: relative;
}
.hint button,
.mistakes,
select,
.dashed,
#canvas,
.fullScreen {
  background: transparent;
}
.hint {
  margin-right: 10px;
  height: 30px;
}
.hint button {
  color: white;
  width: 50px;
  height: 30px;
  border: 2px solid white;
  outline: none;
  cursor: pointer;
}
.hint button:disabled {
  background: grey;
}
.mistakes {
  margin-left: 10px;
  line-height: 0.9;
}
@media only screen and (max-width: 340px) {
  .columns {
    flex-wrap: wrap;
    margin: 0 auto;
  }
  .mistakes {
    width: 100px;
    margin-left: 0px;
  }
}
.dashed {
  height: 28px;
}
.select-wrapper {
  position: relative;
  width: 204px;
  height: 16px;
}
/* .select-wrapper::after {
  position: absolute;
  font-family: "Font Awesome 5 free";
  font-weight: 900;
  content: "\f13a";
  top: 8px;
  right: 8px;
  color: crimson;
  pointer-events: none;
} */
select:disabled {
  background: grey;
}
select {
  -webkit-appearance: none;
  text-indent: 10px;
  display: block;
  margin: 0 auto;
  cursor: pointer;
  color: white;
  border: 2px solid white;
  outline: none;
  width: 204px;
  height: 30px;
}
option {
  background: grey;
}
.dashed div {
  position: relative;
  margin-top: 10px;
  margin-bottom: 10px;
  text-align: center;
}
.keyboard,
.key {
  display: flex;
  justify-content: center;
  align-items: center;
}
.keyboard {
  flex-wrap: wrap;
  margin: 0 auto;
  padding-top: 10px;
}
.key {
  padding: 10px;
  width: 20px;
  height: 20px;
  text-align: center;
  border: 2px solid white;
  border-radius: 50%;
  cursor: pointer;
}
@media only screen and (max-width: 600px) {
  .keyboard {
    width: 90%;
  }
  .key {
    width: 30px;
    height: 30px;
    font-size: 20px;
  }
}
@media only screen and (min-width: 600px) {
  .keyboard {
    width: 50%;
  }
}
</style>

