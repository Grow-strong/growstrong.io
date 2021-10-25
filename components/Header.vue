<template>
  <header>
    <h1 class="title"> Grow Strong! </h1>
    <b-navbar>
      <template #start>
        <b-navbar-item href="#">
          Home
        </b-navbar-item>
        <b-navbar-item href="#">
          Documentation
        </b-navbar-item>
        <b-navbar-dropdown label="Info">
          <b-navbar-item href="#">
            About
          </b-navbar-item>
          <b-navbar-item href="#">
            Contact
          </b-navbar-item>
        </b-navbar-dropdown>
      </template>

    </b-navbar>
    <section>
      <b-field>
        <b-switch v-model="isDarkMode"
                  true-value="Light"
                  false-value="Dark">
          {{ isDarkMode }}
        </b-switch>
      </b-field>
      <b-field>
        <b-switch
          v-model="lightMode"
          passive-type='is-dark'
          type='is-warning'
          @change="changeColorMode($event)">
          {{ lightMode ? "Light Mode" : "Dark Mode" }}
        </b-switch>
      </b-field>
    </section>
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
