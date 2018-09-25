<template>
  <div class="home home-view">
    <header class="home-header">
      <div class="home-title-wrapper">
        <h1 class="home-title">Home</h1>
        <div class="rotate-wrapper">
          <div class="rotater react-bubble">
            <h1 class="rotater-title">React</h1>
          </div>
          <div class="rotater vue-bubble">
            <h1 class="rotater-title">Vue</h1>
          </div>
          <div class="rotater js-bubble">
            <h1 class="rotater-title">JS/ES6</h1>
          </div>
          <div class="rotater css-bubble">
            <h1 class="rotater-title">CSS3</h1>
          </div>
          <div class="rotater html-bubble">
            <h1 class="rotater-title">HTML5</h1>
          </div>
          <div class="rotater git-bubble">
            <h1 class="rotater-title">Git</h1>
          </div>
        </div>
      </div>
      <!-- <div class="scroll-icon">
        <svg xmlns="http://www.w3.org/2000/svg" width="34.375" height="80.375" viewBox="0 0 34.375 80.375">
          <path id="mouse-scroll" d="M32.927,37.933c0,6.972-5.652,12.625-12.625,12.625h-6.333C6.997,50.558,1.344,44.905,1.344,37.933V13.917  c0-6.972,5.652-12.625,12.625-12.625l6.333,0c6.973,0,12.625,5.653,12.625,12.625V37.933zM19.198,15.125c0,1.104-0.895,2-2,2h-0.125c-1.104,0-2-0.896-2-2V9.166c0-1.104,0.896-2,2-2h0.125c1.105,0,2,0.896,2,2V15.125zM17.136 7.166 L17.166 1.437zM17.136 17.125 L17.136 23.208z"/>
          <polyline id="arrow1" points="26.948,58.5 17.136,68.313   7.323,58.5 "/>
          <polyline id="arrow2" points="26.948,65.25 17.136,75.063   7.323,65.25 "/>
        </svg>
      </div> -->
    </header>
    <section class="home-intro">
      <
    </section>
  </div>
</template>

<script>
export default {
    name: 'Home',
    components: {

    },
    data() {
        return {

        };
    },
};
</script>

<style lang="scss">
@import "@/assets/stylesheets/variables.scss";
@import "@/assets/stylesheets/palette.scss";
@import "@/assets/stylesheets/mixins.scss";
@import "@/assets/stylesheets/animations.scss";
@import "@/assets/stylesheets/reset.scss";

.home-view {
  width: 100%;
  height: 100%;
}

.home-header {
  width: 100%;
  height: 100%;
  position: relative;
  background-color: $primary;
}

.home-title-wrapper {
  width: 200px;
  height: 200px;
  position: absolute;
  left: calc(50% - 100px);
  top: calc(50% - 100px);
  color: $grey;
  background-color: $white;
  border-radius: 50%;
  text-align: center;
}

.home-title {
  position: absolute;
  top: calc(50% - 8px);
  left: calc(50% - 23px);
  text-align: center;
}

.rotate-wrapper {
  width: 100%;
  height: 100%;
  position: relative;
  transform: rotate(0);
  animation: rotate-clockwise 10s infinite linear;
}

.rotater {
  width: 100px;
  height: 100px;
  position: absolute;
  /* top: calc(25% - 50px);
  left: calc(50% - 50px); */

  background-color: $secondary;
  color: $white;
  border-radius: 50%;
  text-align: center;
  /* animation: rotate-around 2s ease-in-out infinite; */
  /* transform-origin: calc(100% + 100px) 100px; */
}

.rotater-title {
  position: relative;
  top: 40px;
  animation: rotate-counterclockwise 10s infinite linear;
}

.react-bubble {
  transform: translateX(50%) translateY(-150%) rotate(0deg);
}

.vue-bubble {
  transform: translateX(225%) translateY(-50%) rotate(0deg);
}

.js-bubble {
  transform: translateX(-125%) translateY(-50%) rotate(0deg);
}

.css-bubble {
  transform: translateX(50%) translateY(250%) rotate(0deg);
}

.html-bubble {
  transform: translateX(-125%) translateY(150%) rotate(0deg);
}

.git-bubble {
  transform: translateX(225%) translateY(150%) rotate(0deg);
}

/* svg {
  path,
  polyline {
    fill: none;
    stroke: white;
    stroke-width: 2;
    stroke-linecap: round;
  }
}

svg {

}

path {
  opacity: 0;
  animation: stroke .9s .35s forwards;
  animation-timing-function: cubic-bezier(1, .1, .8, 1);
}

svg {
  margin: 5em;
}

polyline {
  opacity: 0;
  animation: arrows .7s infinite, arrow_intro 2.25s forwards;

  + polyline {
    animation-delay: .1s;
  }
} */

</style>
