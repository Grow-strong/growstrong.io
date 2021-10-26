<template>
  <div>
    <section :class="'container is-widescreen ' + this.viewMode">

      <div class="container column is-10">
        <Header v-on:light-mode="updateViewMode"/>
        <Nuxt />
        <Footer/>

      </div>
    </section>
  </div>
</template>

<script>
import Header from "../components/Header";
export default {
  data() {
    return {
      viewMode: 'dark'
    }
  },
  components: {
    Header
  },
  methods: {
    updateViewMode(mode) {
      this.viewMode = mode ? 'light' : 'dark'
    }
  }
}
</script>
