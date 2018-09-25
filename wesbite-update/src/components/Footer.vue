<template>
  <footer class="main-footer">
    <div class="footer-left">
      <nav class="footer-nav">
        <router-link class="footer-nav-link" to="/home">Home</router-link>
        <router-link class="footer-nav-link" to="/about">About</router-link>
        <router-link class="footer-nav-link" to="/projects">Projects</router-link>
        <router-link class="footer-nav-link" to="/blog">Blog</router-link>
        <router-link class="footer-nav-link" to="/contact">Contact</router-link>
      </nav>
    </div>
    <div class="footer-right">
      <div class="butter">
        <span class="attribution">Blog Powered by</span>
        <a href="https://buttercms.com" class="attribution-image"></a>
      </div>
    </div>
  </footer>
</template>

<script>
import $ from 'jquery'
import Router from 'vue-router'

export default {
    name: 'AppFooter',
    components: {

    },
    data() {
        return {
        };
    },
    methods: {

    },
};
</script>

<style lang="scss">
@import "@/assets/stylesheets/variables.scss";
@import "@/assets/stylesheets/palette.scss";
@import "@/assets/stylesheets/mixins.scss";
@import "@/assets/stylesheets/animations.scss";
@import "@/assets/stylesheets/reset.scss";
@import "@/assets/stylesheets/fonts.scss";
@import "@/assets/stylesheets/footer.scss";
</style>
