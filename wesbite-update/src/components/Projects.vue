<template>
  <div class="projects-view slider">
    <div class="projects-wrapper">
      <AppHeader></AppHeader>
      <section class="projects">
        <h1 class="projects-heading">My Work</h1>
        <div class="project-wrapper" v-for="project in projects">
          <router-link :to="'/projects/' + project.url" :id="project.url" class="project-image"></router-link>
          <p class="project-name">{{project.title}}</p>
        </div>
        <!-- <div class="project-wrapper">
          <router-link to="/projects/rostered" id="rostered" class="project-image-reverse"></router-link>
          <p class="project-name-reverse">Rostered</p>
        </div> -->
      </section>
      <section class="connect">
        <h1 class="connect-main-heading">Want to start a conversation about how you can be next?</h1>
        <router-link to="/contact" class="connect-link">Let's Connect</router-link>
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
import { butter } from '@/butter.js';

export default {
    name: 'Projects',
    components: {
      AppHeader,
      AppFooter
    },
    data() {
        return {
          projects: []
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
      getProjects() {
        butter.content.retrieve(['projects'])
          .then((resp) => {
            this.projects = resp.data.data.projects;
            console.log(this.projects);
          }).catch((resp) => {
            console.log(resp)
          });
      }
    },
    mounted() {
      $(".ham").css("background-color", "#002244");
    },
    created() {
      this.getProjects();
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
@import "@/assets/stylesheets/projects.scss";
</style>
