<template>
  <div id="app">
    <div class="app__wrapper">
      <router-view/>
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


</style>
