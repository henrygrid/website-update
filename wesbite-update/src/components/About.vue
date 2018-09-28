<template>
  <div class="about-view slider">
    <div class="about-wrapper">
      <AppHeader></AppHeader>
      <section class="greetings">
        <div class="greetings-left">
          <h1 class="greetings-heading">Nice to meet you!</h1>
          <h2 class="greetings-intro">I'm a developer, communicator and all around problem solver living in the Metro Detroit area. Let's start a conversation about how I can help you today.</h2>
          <p class="greetings-text">Every man who has lotted here over the centuries, has looked up to the light and imagined climbing to freedom. So easy, so simple! And like shipwrecked men turning to seawater foregoing uncontrollable thirst, many have died trying. And then here there can be no true despair without hope. So as I terrorize Gotham, I will feed its people hope to poison their souls. I will let them believe that they can survive so that you can watch them climbing over each other to stay in the sun. You can watch me torture an entire city. And then when you've truly understood the depth of your failure, we will fulfill Ra's Al Ghul's destiny. We will destroy Gotham. And then, when that is done, and Gotham is... ashes Then you have my permission to die.</p>
          <span v-if="aboutShowing === false" @click="toggleAbout" class="greetings-text-toggle"><font-awesome-icon class="greetings-text-toggle-icon" icon="plus" />Show More</span>
          <span v-if="aboutShowing === true" @click="toggleAbout" class="greetings-text-toggle"><font-awesome-icon class="greetings-text-toggle-icon" icon="minus" />Show Less</span>
        </div>
        <div class="greetings-right">
          <span class="greetings-image"></span>
          <a href="" class="greetings-social linkedin"></a>
          <a href="" class="greetings-social insta"></a>
          <a href="" class="greetings-social github"></a>
          <a href="" class="greetings-social codepen"></a>
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
          aboutShowing: false
        };
    },
    methods: {
      handleScroll (e) {
        if($(window).scrollTop() >= 542) {
          $(".ham").css("background-color", "#F3F4F1");
        } else {
          $(".ham").css("background-color", "#002244");
        }
      },
      toggleAbout() {
        $('.greetings-text').slideToggle();
        this.aboutShowing = !this.aboutShowing;
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
