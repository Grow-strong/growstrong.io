<template>
  <div>
    <!-- <nav
      class="navbar header has-shadow is-primary"
      role="navigation"
      aria-label="main navigation"
    >
      <div class="navbar-brand">
        <a
          class="navbar-item"
          href="/"
        >
          <img
            src="~assets/buefy.png"
            alt="Buefy"
            height="28"
          >
        </a>

        <div class="navbar-burger">
          <span />
          <span />
          <span />
        </div>
      </div>
    </nav> -->

    <section :class="this.viewMode">
      <!--<aside class="column is-2 section">
        <p class="menu-label is-hidden-touch">
          General
        </p>
        <ul class="menu-list">
          <li
            v-for="(item, key) of items"
            :key="key"
          >
            <NuxtLink
              :to="item.to"
              exact-active-class="is-active"
            >
              <b-icon :icon="item.icon" /> {{ item.title }}
            </NuxtLink>
          </li>
        </ul>
      </aside>-->

      <div class="container column is-10">
        <Header v-on:light-mode="updateViewMode"/>
        <Nuxt />
      </div>
    </section>
  </div>
</template>

<script>
import Header from "../components/Header";
export default {
  data() {
    return {
      viewMode: false
    }
  },
  components: {
    Header
  },
  methods: {
    updateViewMode(mode) {
      console.log('+++++++++++++++++ MODE ++++++++++++++++++')
      console.log(mode)
      console.log('+++++++++++++++++ MODE ++++++++++++++++++')
      this.viewMode = mode ? 'light' : 'dark'
    }
  }
  /*data () {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' }
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' }
        }
      ]
    }
  }*/
}
</script>
