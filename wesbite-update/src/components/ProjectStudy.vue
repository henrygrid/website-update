<template>
  <div class="projects-view slider">
    <div class="projects-wrapper">
      <div class="projects-banner"></div>
      <AppHeader></AppHeader>
      <section class="projects">
        <div class="projects-header">
          <h1 class="projects-heading">{{project.title}}</h1>
        </div>
        <article class="projects-content">
            <p>{{project.description}}</p>
        </article>
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
    name: 'ProjectStudy',
    components: {
      AppHeader,
      AppFooter
    },
    data() {
        return {
          projects: [],
          project: {}
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
            this.projects.map((project) => {
              if(project.url === this.$route.params.name) {
                this.project = project;
                console.log(project);
              }
            });
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
