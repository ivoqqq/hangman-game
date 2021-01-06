<template>
  <div class="modalHintContainer" v-if="showHint">
    <div class="innerHintContainer">
      <div class="bigWheelContainer">
        <div id="arrow">
          <svg xmlns="http://www.w3.org/2000/svg">
            <path
              style="
                fill: #ff2e52;
                stroke: #012e52;
                stroke-width: 4;
                stroke-linecap: round;
                stroke-linejoin: round;
              "
              d="M 81.540414,49.378716 H 121.51935 L 101.4866,69.420346 Z"
            />
          </svg>
        </div>
        <svg id="wheelContainer" viewBox="5 46.5 100 100">
          <g class="wheel">
            <g id="inside">
              <!-- +2 MISTAKES ICON-->
              <path
                style="fill: #5a8216"
                d="M 75.401018,108.09082 55,96.346226 54.980893,70.522929 55.016946,47 l 1.584688,0.10122 c 11.463024,0.731783 21.658155,4.629281 30.147826,11.525236 1.517251,1.232449 4.648236,4.219432 5.873866,5.603699 10.780094,12.175489 14.383374,28.590777 9.647444,47.686135 -0.7237,2.34681 -1.85193,5.05222 -3.10422,7.44256 L 98,121.58588 Z"
              />
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="-2100 -1700 2500 2500"
              >
                <g transform="rotate(60)">
                  <polygon
                    style="fill: #54bbff"
                    points="474.5,7.5 256,256 474.5,504.5 504.5,504.5 504.5,7.5 "
                  />
                  <rect
                    x="7.5"
                    y="7.5"
                    style="fill: #8dd2ff"
                    width="467"
                    height="497"
                  />
                  <polygon
                    style="fill: #c6e8ff"
                    points="444.5,37.5 256,256 444.5,474.5 474.5,474.5 474.5,37.5 "
                  />
                  <rect
                    x="37.5"
                    y="37.5"
                    style="fill: #def1ff"
                    width="407"
                    height="437"
                  />
                  <path
                    style="fill: #54bbff"
                    d="M305.5,391.5h-99c-7.177,0-13.804-3.846-17.365-10.077s-3.51-13.893,0.134-20.076l92.162-156.403
											c2.663-4.517,4.069-9.683,4.069-14.943c0-16.266-13.234-29.5-29.5-29.5s-29.5,13.234-29.5,29.5c0,11.046-8.954,20-20,20
											s-20-8.954-20-20c0-38.322,31.178-69.5,69.5-69.5s69.5,31.178,69.5,69.5c0,12.4-3.323,24.59-9.609,35.253L241.499,351.5H305.5
											c11.046,0,20,8.954,20,20S316.546,391.5,305.5,391.5z"
                  />
                  <path
                    d="M504.5,0H7.5C3.358,0,0,3.358,0,7.5v497c0,4.142,3.358,7.5,7.5,7.5h497c4.142,0,7.5-3.358,7.5-7.5V7.5
											C512,3.358,508.642,0,504.5,0z M497,497H15V15h482V497z"
                  />
                  <path
                    d="M37.5,482h437c4.142,0,7.5-3.358,7.5-7.5v-437c0-4.142-3.358-7.5-7.5-7.5h-437c-4.142,0-7.5,3.358-7.5,7.5v45
											c0,4.142,3.358,7.5,7.5,7.5s7.5-3.358,7.5-7.5V45h422v422H45V112.5c0-4.142-3.358-7.5-7.5-7.5s-7.5,3.358-7.5,7.5v362
											C30,478.642,33.358,482,37.5,482z"
                  />
                  <path
                    d="M333,190c0-42.458-34.542-77-77-77s-77,34.542-77,77c0,15.164,12.336,27.5,27.5,27.5S234,205.164,234,190
											c0-12.131,9.869-22,22-22c12.131,0,22,9.869,22,22c0,3.922-1.048,7.772-3.03,11.136l-92.162,156.403
											c-4.998,8.481-5.068,19.059-0.184,27.605C187.507,393.691,196.656,399,206.5,399h99c15.164,0,27.5-12.336,27.5-27.5
											S320.664,344,305.5,344h-50.876l67.729-114.938C329.318,217.246,333,203.738,333,190z M309.43,221.446l-74.392,126.247
											c-1.367,2.319-1.386,5.192-0.05,7.529s3.82,3.779,6.512,3.779h64c6.893,0,12.5,5.607,12.5,12.5s-5.607,12.5-12.5,12.5h-99
											c-4.474,0-8.633-2.414-10.853-6.298c-2.22-3.885-2.188-8.692,0.083-12.547l92.162-156.402C291.234,203.083,293,196.599,293,190
											c0-20.402-16.598-37-37-37s-37,16.598-37,37c0,6.893-5.607,12.5-12.5,12.5S194,196.893,194,190c0-34.187,27.813-62,62-62
											s62,27.813,62,62C318,201.061,315.037,211.935,309.43,221.446z"
                  />
                </g>
              </svg>
              <!-- JOKER ICON-->
              <path
                style="fill: #aa8800"
                d="M 12,121.58588 C 9.7697134,116.86628 7.3300026,111.98962 6.5107679,106.39092 6.1233125,103.74344 5.6144823,94.963503 5.8712492,92.057537 6.9404107,79.962633 12.203181,69.761046 20.248838,61.242147 28.952505,52.026531 40.81057,47.904039 53.234457,47.112087 L 54.986174,47 l 1.01e-4,10.928628 c 2.1e-5,6.010757 0.04373,17.449324 0.09622,25.419102 L 55,96.346226 33.625709,109.10978 c -11.46129,6.88695 -21.432757,12.36577 -21.624899,12.47574 -0.340853,0.19524 0.782159,1.65445 0,0 z"
              />
              <svg
                id="joker"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="-270 -1740 2000 2000"
              >
                <g transform="rotate(-60)">
                  <circle style="fill: #324a5e" cx="254" cy="254" r="254" />
                  <circle style="fill: #ffd05b" cx="253.2" cy="334" r="90.4" />
                  <path
                    style="fill: #f1543f"
                    d="M352.8,168.8c-11.2-0.4-23.2,1.6-34.8,6c1.2-4.4,2.8-8.4,4.8-12.4c17.6-40,56.8-72.8,107.2-52.4
											c-43.2-40-98.4-34-139.6,10.8c-15.2,16.4-28.4,38-37.6,63.6c-9.2-25.6-22.4-47.6-37.6-63.6C174.4,76,119.2,70.4,76,110
											c50-20.8,89.6,12.4,107.2,52.4c2,4,3.6,8.4,4.8,12.4c-11.6-4.4-23.2-6.4-34.8-6c-46.4,1.2-86.4,39.2-99.6,99.6
											C79.2,216,120,208,148.4,222c19.2,9.2,32.8,27.2,40,49.2H318c6.8-22,20.8-40,40-49.2c28.4-14,68.8-6,94.8,46.4
											C439.6,208,399.6,170,352.8,168.8z"
                  />
                  <g>
                    <circle
                      style="fill: #ffffff"
                      cx="450"
                      cy="264.8"
                      r="20.8"
                    />
                    <circle
                      style="fill: #ffffff"
                      cx="428.8"
                      cy="106.8"
                      r="17.6"
                    />
                    <circle style="fill: #ffffff" cx="58" cy="264.8" r="20.8" />
                    <circle
                      style="fill: #ffffff"
                      cx="79.2"
                      cy="106.8"
                      r="17.6"
                    />
                  </g>
                  <circle
                    style="fill: #324a5e"
                    cx="284.8"
                    cy="322.4"
                    r="14.8"
                  />
                  <ellipse
                    transform="matrix(0.7267 -0.6869 0.6869 0.7267 -141.2726 277.4767)"
                    style="fill: #ffffff"
                    cx="278.111"
                    cy="316.297"
                    rx="5.2"
                    ry="2.4"
                  />
                  <circle
                    style="fill: #324a5e"
                    cx="221.2"
                    cy="322.4"
                    r="14.8"
                  />
                  <ellipse
                    transform="matrix(0.7267 -0.687 0.687 0.7267 -158.8096 233.8235)"
                    style="fill: #ffffff"
                    cx="214.446"
                    cy="316.491"
                    rx="5.2"
                    ry="2.4"
                  />
                </g>
              </svg>
              <!-- POINTER ICON-->
              <path
                style="fill: #c02b58"
                d="M 52.957884,145.7433 c -14.204778,-0.58679 -27.596723,-7.43977 -36.471671,-18.66335 -1.138709,-1.43989 -3.471778,-4.82145 -3.866564,-5.60389 -0.108148,-0.21533 0.994313,-0.86759 21.129265,-12.48795 11.684241,-6.74343 21.30071,-12.260661 21.369968,-12.260661 0.133447,0 41.663135,24.537951 41.888875,24.750121 0.244767,0.23042 -2.515505,4.26887 -4.656697,6.81382 -1.262105,1.50017 -3.863625,4.14197 -5.323605,5.40618 -5.836038,5.05349 -12.738043,8.67691 -20.098353,10.55146 -3.26762,0.8323 -6.079682,1.26106 -9.558213,1.45649 -1.854258,0.10073 -2.639573,0.11341 -4.413005,0.0379 z"
              />
              <svg
                id="pointer"
                height="150px"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="-1400 -2100 2000 2000"
              >
                <g transform="rotate(180)">
                  <path
                    style="fill: #cff09e"
                    d="m 343.90957,92.298713 v -15.951 c 0,-15.948 -13.009,-29.53 -29.728,-30.096 -17.553,-0.595 -31.979,12.793 -31.979,29.391 v 17.213 l -0.333,-154.105998 c 0,-16.243 -13.813,-29.411 -30.854,-29.411 h -1.187 c -17.039,0 -30.854,13.168 -30.854,29.411 v 110.670998 25.447 76.907997 l -30.02,-73.096997 c -5.281,-15.769 -22.984,-24.465 -39.527,-19.431 -16.543,5.043 -25.665,21.909 -20.384,37.684 l 65.918,135.744997 c 8.141,16.765 25.756,27.5 45.137,27.509 l 177.423,0.077 c 27.491,0.012 49.783,-21.226 49.786,-47.432 l 0.018,-116.555997 c 0,-16.243 -13.813,-29.411 -30.854,-29.411 v 0 c -17.039,0 -30.854,13.168 -30.854,29.411 v -6.989 c 0,-16.243 -13.813,-29.411 -30.854,-29.411 v 0 c -17.039,0 -30.854,13.168 -30.854,29.411"
                  />
                  <path
                    style="fill: #507c5c"
                    d="m 417.54357,275.31771 c -0.011,0 -0.02,0 -0.03,0 l -177.421,-0.077 c -25.033,-0.012 -48.062,-14.139 -58.672,-35.988 l -65.919,-135.744 c -0.283,-0.583 -0.528,-1.182 -0.733,-1.796 -3.788,-11.307997 -2.854,-23.390997 2.625,-34.021997 5.684,-11.03 15.502,-19.142 27.643,-22.843 24.074,-7.325 49.967,5.457 58.011,28.529 l 0.872,2.121 V -61.251285 c 0.001,-24.517 20.596,-44.463005 45.909,-44.463005 h 1.186 c 25.313,0 45.907,19.946005 45.907,44.464005 l 0.206,95.205998 c 5.564,-1.992998 11.525,-2.957998 17.56,-2.749998 15.338,0.521 28.625,8.285998 36.537,19.915998 6.886,-3.998 14.939,-6.3 23.537,-6.3 13.886,0 26.35,6 34.776,15.465 7.569,-5.329 16.88,-8.475 26.933,-8.475 25.313,0 45.908,19.946 45.908,44.464 l -0.02,116.556997 c -10e-4,16.832 -6.84,32.616 -19.255,44.442 -12.21,11.636 -28.39,18.043 -45.56,18.043 z m -274.457,-183.925997 65.415,134.710997 c 5.612,11.555 18.016,19.027 31.602,19.033 l 177.42,0.077 c 0.006,0 0.012,0 0.018,0 9.403,0 18.208,-3.455 24.794,-9.731 6.393,-6.091 9.914,-14.134 9.916,-22.648 l 0.02,-116.555997 c 0,-7.914 -7.089,-14.354 -15.801,-14.354 -8.712,0 -15.799,6.44 -15.799,14.357 0,8.312997 -6.741,15.053997 -15.054,15.053997 -8.313,0 -15.054,-6.741 -15.054,-15.053997 v -6.991 c 0,-7.917 -7.089,-14.357 -15.8,-14.357 -8.712,0 -15.801,6.44 -15.801,14.357 v 3.011 c 0,8.312997 -6.741,15.053997 -15.054,15.053997 -8.313,0 -15.054,-6.741 -15.054,-15.053997 v -15.953 c 0.002,-8.015 -6.81,-14.768 -15.185,-15.051 -4.622,-0.178 -8.943,1.45 -12.123,4.522 -2.768,2.675 -4.293,6.165 -4.293,9.824 v 17.213 c 0,8.307997 -6.731,15.044997 -15.037,15.053997 -0.005,0 -0.012,0 -0.017,0 -8.302,0 -15.036,-6.719 -15.054,-15.021997 l -0.333,-154.103998 c 0,-7.948 -7.087,-14.39 -15.799,-14.39 h -1.185 c -8.712,0 -15.8,6.44 -15.8,14.357 V 151.77871 c 0,7.19 -5.085,13.377 -12.138,14.769 -7.057,1.394 -14.11,-2.398 -16.841,-9.05 l -30.02,-73.097997 c -0.128,-0.309 -0.244,-0.622 -0.349,-0.939 -2.708,-8.087 -12.073,-12.487 -20.869,-9.809 -4.295,1.308 -7.726,4.092 -9.654,7.834 -1.602,3.104 -1.973,6.592 -1.071,9.906 z"
                  />
                  <path
                    style="
                      stroke: #507c5c;
                      stroke-width: 30;
                      stroke-dasharray: 155.74239576, 19.46779947;
                      stroke-dashoffset: 115.70281219;
                    "
                    d="M 112.50757,-125.42859 H 483.77749"
                  />
                  <path
                    style="fill: #507c5c"
                    d="m 432.48457,361.27371 h -208 c -8.251,0 -14.941,-6.689 -14.941,-14.941 v -85.956 c 0,-8.252 6.691,-14.941 14.941,-14.941 h 208 c 8.251,0 14.941,6.689 14.941,14.941 v 85.956 c 0,8.252 -6.691,14.941 -14.941,14.941 z m -193.059,-29.883 h 178.118 v -56.073 h -178.118 z"
                  />
                  <path
                    style="fill: #cff09e"
                    d="m 239.42557,275.3177 h 178.11799 v 56.073 H 239.42557 Z"
                  />
                </g>
              </svg>
            </g>
            <g id="outlines" style="fill: none; stroke: #ffffff">
              <circle style="stroke-width: 2" cx="55" cy="96.5" r="49" />
              <g style="stroke-width: 1">
                <path d="m 55, 96.5 l 43, 25.08588" />
                <path d="m 55, 47 l 0, 49.346226" />
                <path d="m 55, 96.5 l -43, 25.08588" />
              </g>
            </g>
          </g>
        </svg>
      </div>
      <div class="wheelShadow"></div>
      <div class="answerContainer">
        <div class="answer" v-if="revealJoker">
          <p>{{ joker }}</p>
        </div>
        <div class="answer" v-else-if="revealMistakes">
          <p>{{ "Added extra two mistakes".toUpperCase() }}</p>
        </div>
        <!-- 					<div class="answer" v-else-if="revealLetter">Choose position to reveal</div> -->
        <div class="answer" v-else-if="revealLetter">
          <p>Choose position to reveal</p>
          <p>
            <span
              class="zzz"
              @click="reveal(index)"
              v-for="(ch, index) in countLetter"
              :key="'ch' + index"
              >{{ ch }}</span
            >
          </p>
        </div>
      </div>

      <div class="btn">
        <button class="spinBtn" :disabled="spinBtnActive" @click="spin">
          SPIN
        </button>
        <button class="closeBtn" @click="closeModal">
          <svg viewBox="2 2 60 60" xmlns="http://www.w3.org/2000/svg">
            <circle cx="32" cy="32" fill="#4dd0e1" r="22" />
            <g fill="#012e52">
              <path
                d="m32 8c-13.234 0-24 10.766-24 24s10.766 24 24 24 24-10.766 24-24-10.766-24-24-24zm0 44c-11.028 0-20-8.972-20-20s8.972-20 20-20 20 8.972 20 20-8.972 20-20 20z"
              />
              <path
                d="m39.414 24.586c-.78-.781-2.048-.781-2.828 0l-4.586 4.586-4.586-4.586c-.78-.781-2.048-.781-2.828 0-.781.781-.781 2.047 0 2.828l4.586 4.586-4.586 4.586c-.781.781-.781 2.047 0 2.828.39.391.902.586 1.414.586s1.024-.195 1.414-.586l4.586-4.586 4.586 4.586c.39.391.902.586 1.414.586s1.024-.195 1.414-.586c.781-.781.781-2.047 0-2.828l-4.586-4.586 4.586-4.586c.781-.781.781-2.047 0-2.828z"
              />
            </g>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      deg: 0,
      spinned: null,
      spinBtnActive: false,
      revealJoker: false,
      revealMistakes: false,
      revealLetter: false,
    };
  },
  props: {
    showHint: {
      type: Boolean,
    },
    word: {
      type: String,
    },
    wordHint: {
      type: String,
    },
    countLetter: {
      type: Array,
    },
  },
  computed: {
    joker: function () {
      return this.wordHint;
    },
  },
  methods: {
    closeModal: function () {
      this.deg = 0;
      this.clearAnswers();
      this.$parent.$el.querySelector(".wrap").style.removeProperty("filter");
      this.$emit("showHint", false);
    },
    reveal: function (i) {
      event.target.innerHTML = this.word.charAt(i);
      setTimeout(() => {
        this.closeModal();
      }, 3000);
    },
    spin: function () {
      this.spinBtnActive = true;

      var spins = Math.floor(Math.random() * 7) + 9; //perform between 9 and 15 spins
      var wheelAngle = Math.floor(Math.random() * 3) * 120; //set wheel angle rotation
      var sectorAngle = Math.floor(Math.random() * 58) + 1; //set sector angle rotation
      sectorAngle *= Math.floor(Math.random() * 2) == 1 ? 1 : -1; //between -14deg and +14deg (28deg range of 30deg sector)
      this.deg += 360 * spins + wheelAngle + sectorAngle;
      this.$el.querySelector(
        ".wheel"
      ).style.transform = `rotate(${this.deg}deg)`;
      setTimeout(() => (this.deg -= sectorAngle), 100);
      var index = Math.floor((this.deg - sectorAngle) / 120) % 3;

      setTimeout(() => {
        this.spinned = index;
        this.spinBtnActive = false;
      }, 5100);

      this.clearAnswers();
    },
    clearAnswers: function () {
      this.revealJoker = false;
      this.revealLetter = false;
      this.revealMistakes = false;
    },
  },
  watch: {
    spinned: function (i) {
      //когато ползвам хинт и при натискане на play again се сменя и влиза в някой if
      //hm работи си
      if (i === 0) {
        this.revealJoker = true;
      } else if (i === 1) {
        this.revealLetter = true;
      } else if (i === 2) {
        this.revealMistakes = true;
        this.$emit("addMistakes", 2);
      }
    },
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  /* box-sizing: border-box; */
}
.modalHintContainer {
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
.innerHintContainer {
  /*   border: 2px solid white; */
  height: 70vh;
  width: 70vw;
  top: calc(50% - 35vh);
  left: calc(50% - 35vw);
  position: absolute;
  border-radius: 30px;
  background: rgba(0, 0, 2, 0.5);
}

/* .bigWheelContainer {
  position: absolute;
  width: inherit;
  height: inherit;
} */
#wheelContainer {
  position: absolute;
  width: 250px;
  height: 250px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(60deg);
  z-index: 10;
}

.wheel {
  transform-origin: 55px 96.5px;
  transition: 5s;
}
.wheelShadow {
  position: absolute;
  height: 240px;
  width: 240px;
  top: calc(50% - 120px);
  left: calc(50% - 120px);
  border-radius: 50%;
  background: transparent;
  box-shadow: 0 0 3px 5px rgba(0, 0, 0, 0.5) inset;
  z-index: 10;
}
#arrow {
  position: absolute;
  z-index: 20;
  top: calc(50% - 175px);
  left: calc(50% - 101px);
}

.spinBtn {
  height: 50px;
  width: 50px;
  position: absolute;
  border-radius: 50%;
  top: calc(50% - 25px);
  left: calc(50% - 25px);
  border: none;
  outline: none;
  box-shadow: 0 0 5px 2px rgb(0, 0, 0);
  background: linear-gradient(
    to bottom,
    rgb(252, 255, 244) 0%,
    rgb(223, 229, 215) 30%,
    rgb(179, 190, 173) 100%
  );
  z-index: 10;
  cursor: pointer;
}
.spinBtn:disabled {
  background: white;
  box-shadow: 0 0 5px 2px rgb(0, 0, 0);
  background: linear-gradient(
    to bottom,
    rgb(252, 255, 244) 0%,
    rgb(223, 229, 215) 30%,
    rgb(179, 190, 173) 100%
  );
}
.spinBtn:active {
  transform: scale(0.9);
}
.closeBtn {
  position: absolute;
  width: 30px;
  height: 30px;
  top: 40px;
  right: 50px;
  border: 1px solid #4dd0e1;
  border-radius: 50%;
  outline: none;
  cursor: pointer;
  z-index: 30;
}
.answer {
  /* height: 10vh; */
  min-height: 10vh;
  min-width: 60vw;
  top: calc(50% + 20vh);
  left: calc(50% - 30vw);
  position: absolute;
  border: 3px solid white;
  border-radius: 30px;
  background: #4dd0e1;
  box-shadow: 0 0 2px 5px rgba(0, 0, 0, 0.5) inset;
  text-align: center;
  color: black;
  z-index: 20;
  /* display: flex;
  flex-direction: column; */
  display: grid;
  grid-template-rows: auto;
}
.zzz {
  /* display: inline-block; */
  padding: 2%;
  /* margin-right: 2%; */
  cursor: pointer;
  width: 60vw;
}
</style>