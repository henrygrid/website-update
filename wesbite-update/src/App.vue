<template>
  <div id="app">
    <div class="app__wrapper">
      <transition name="slide">
        <router-view/>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {

  }
}
</script>

<style lang="scss">
@import "@/assets/stylesheets/variables.scss";
@import "@/assets/stylesheets/palette.scss";
@import "@/assets/stylesheets/mixins.scss";
@import "@/assets/stylesheets/animations.scss";
@import "@/assets/stylesheets/reset.scss";
@import "@/assets/stylesheets/fonts.scss";

body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  width: 100%;
  height: 100vh;
}

.app__wrapper {
  width: 100%;
  height: 100%;
  position: relative;
}

.slider {
  position: absolute;
  top: 0;
  right: 0;
}

.slide-enter-active {
  animation: slow-slide-in 2s;

  .nav-show {
    display: none;
  }
}

.slide-leave-active {
  animation: slow-slide-out 2s;
}

</style>
