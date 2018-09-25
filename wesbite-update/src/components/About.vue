<template>
  <div class="about-view">
    <div class="about-wrapper">
      <AppHeader></AppHeader>
      <section class="greetings">
        <div class="greetings-left">
          <h1 class="greetings-heading">Nice to meet you!</h1>
          <h2 class="greetings-intro">I'm a developer, communicator and all around problem solver living in the Metro Detroit area. Let's start a conversation about how I can help you today.</h2>
          <p class="greetings-text"></p>
        </div>
        <div class="greetings-right">
          <span class="greetings-image"></span>
        </div>
      </section>
      <section class="skills">
        <h1 class="skills-main-heading">What am I bringing to the table?</h1>
        <div class="skills-column">
          <h2 class="skills-heading">Skills and Technologies</h2>
          <div class="skills-left">
            <ul class="skills-list">
              <li class="skills-list-item">HTML5</li>
              <li class="skills-list-item">CSS3</li>
              <li class="skills-list-item">Sass/Less</li>
              <li class="skills-list-item">JS</li>
              <li class="skills-list-item">Jquery</li>
              <li class="skills-list-item">ReactJS</li>
              <li class="skills-list-item">AJAX</li>
            </ul>
          </div>
          <div class="skills-right">
            <ul class="skills-list">
              <li class="skills-list-item">VueJS</li>
              <li class="skills-list-item">Gulp</li>
              <li class="skills-list-item">Webpack</li>
              <li class="skills-list-item">Git</li>
              <li class="skills-list-item">Sketch/Photoshop</li>
              <li class="skills-list-item">Communication</li>
              <li class="skills-list-item">Performance Optimisation</li>
            </ul>
          </div>
        </div>
        <div class="methodologies">
          <h2 class="methodologies-heading">Methodologies</h2>
          <div class="methodologies-left">
            <ul class="methodologies-list">
              <li class="methodologies-list-item">Object Oriented Programming</li>
              <li class="methodologies-list-item">MVC</li>
              <li class="methodologies-list-item">Agile</li>
            </ul>
          </div>
        </div>
      </section>
      <AppFooter></AppFooter>
    </div>
  </div>
</template>

<script>
import $ from 'jquery';
import AppHeader from '@/components/Header.vue'
import AppFooter from '@/components/Footer.vue'
import Router from 'vue-router'

export default {
    name: 'About',
    components: {
      AppHeader,
      AppFooter
    },
    data() {
        return {

        };
    },
    methods: {
      handleScroll (e) {
        if($(window).scrollTop() >= 542) {
          $(".ham").css("background-color", "#F3F4F1");
        } else {
          $(".ham").css("background-color", "#002244");
        }
      }
    },
    mounted() {
      $(".ham").css("background-color", "#002244");
    },
    created() {
      window.addEventListener('scroll', this.handleScroll);
    },
    destroyed() {
      window.removeEventListener('scroll', this.handleScroll);
    }
};
</script>

<style lang="scss">
@import "@/assets/stylesheets/variables.scss";
@import "@/assets/stylesheets/palette.scss";
@import "@/assets/stylesheets/mixins.scss";
@import "@/assets/stylesheets/animations.scss";
@import "@/assets/stylesheets/reset.scss";
@import "@/assets/stylesheets/fonts.scss";
@import "@/assets/stylesheets/about.scss";
</style>

<style lang="scss" scoped>

/* .ham {
  background-color: #002244;
} */

</style>
