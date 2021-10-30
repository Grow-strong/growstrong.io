<template>
  <header class="container">
    <h1 class="title"> Grow Strong! </h1>
    <!--
    vue element error comes from header

    <b-navbar :fixed-top="true"  :transparent="true">-->
    <b-navbar>
      <template #start>
        <b-navbar-item href="#">
          <nuxt-link :to="{ path: '/',hash:'#home'}">Home</nuxt-link>
        </b-navbar-item>
        <b-navbar-item href="#">
          <nuxt-link :to="{ path: '/',hash:'#aim'}">Aim</nuxt-link>
        </b-navbar-item>
        <b-navbar-item href="#">
          <nuxt-link :to="{ path: '/',hash:'#road-map'}">Road map</nuxt-link>
        </b-navbar-item>
        <b-navbar-item href="#">
          <nuxt-link :to="{ path: '/',hash:'#inputs'}">Your inputs</nuxt-link>
        </b-navbar-item>
        <b-navbar-item href="#">
          <nuxt-link :to="{ path: '/',hash:'#testimonials'}">Testimonials</nuxt-link>
        </b-navbar-item>

        <!--<b-navbar-item>
          <b-field>
            <b-switch
              v-model="lightMode"
              passive-type='is-dark'
              type='is-warning'
              @change="changeColorMode($event)">
              {{ lightMode ? "Light Mode" : "Dark Mode" }}
            </b-switch>
          </b-field>
        </b-navbar-item> -->
      </template>
    </b-navbar>

  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isDarkMode: 'Light',
      lightMode: false
    }
  },
  watch: {
    lightMode: function () {
      this.$emit('light-mode', this.lightMode)
    }
  },
}
</script>

<style>

</style>
