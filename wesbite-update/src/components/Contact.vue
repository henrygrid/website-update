<template>
  <div class="contact-view slider">
    <div class="contact-wrapper">
      <AppHeader></AppHeader>
      <section class="contact">
        <h1 class="contact-heading">Coffee, Tea or something else? Either way, let's chat.</h1>
        <form class="contact-form" method="POST" action="https://formspree.io/hjmorrow23@gmail.com">
          <fieldset class="contact-fieldset">
            <label class="contact-label" for="Name">Name</label>
            <input type="text" name="Name" placeholder="Jane and John Doe" class="contact-input" />
          </fieldset>
          <fieldset class="contact-fieldset">
            <label class="contact-label" for="Email">Email</label>
            <input type="email" name="Email" placeholder="holdthedoe@gmail.com" class="contact-input" />
          </fieldset>
          <fieldset class="contact-fieldset">
            <label class="contact-label" for="Company">Company (if applicable)</label>
            <input type="text" name="Company" placeholder="Doe & Co." class="contact-input" />
          </fieldset>
          <fieldset class="contact-fieldset">
            <label class="contact-label" for="Reason">Reason for reaching out</label>
            <input type="text" name="Reason" placeholder="Hey cool site! Can you make one for me?" class="contact-input-long" />
          </fieldset>
          <input type="submit" class="contact-submit" value="Start something great"/>
        </form>
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
    name: 'Contact',
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
          $(".ham").css("background-color", "#002244");
        } else {
          $(".ham").css("background-color", "#F3F4F1");
        }
      }
    },
    mounted() {
      // $(".ham").css("background-color", "#002244");
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
@import "@/assets/stylesheets/contact.scss";
</style>
