<template>
  <v-app light>
    <div class="hide-overflow" style="position: relative;">
    <v-toolbar app
      absolute
      color="primary"
      scroll-off-screen
      >
      <v-toolbar-side-icon class="hidden-sm-and-up" @click="drawer = !drawer" />
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">
          {{ title }}
        </router-link>
      </v-toolbar-title>
      <v-spacer />
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat router to="/">
          <v-icon left>
            fas fa-home
          </v-icon>Home
        </v-btn>
        <v-btn flat router to="/about">
          <v-icon left>
            fas fa-clipboard-list
          </v-icon>About
        </v-btn>
        <v-btn flat router to="/services">
          <v-icon left>
            fas fa-code
          </v-icon>Services
        </v-btn>
        <v-btn flat router to="/swiper">
          <v-icon left>
            fas fa-heartbeat
          </v-icon>Swiper
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <v-container>
      <transition name="fade">
        <router-view/>
      </transition>
      </v-container>
      <v-fab-transition>
        <v-btn
          v-show="fab"
          v-scroll="onScroll"
          color="secondary"
          fab
          dark
          small
          fixed
          bottom
          right
          @click="toTop"
        >
          <v-icon>
            fas fa-angle-up
          </v-icon>
        </v-btn>
      </v-fab-transition>
    </v-content>

    </div>
    <v-navigation-drawer v-model="drawer" app absolute temporary>
      <v-list>
        <v-list-tile v-for="item in items" :key="item.title" router-link :to="item.to" exact>
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="title">
              {{ item.title }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      app
      height="auto"
    >
      <v-layout
        justify-center
        row
        wrap
      >
        <v-flex
          accent
          py-3
          text-xs-center
          dark--text
          xs12
        >
          &copy;2019 — <strong>PRO 1423 TRAINING</strong>
        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      fab: false,
      drawer: null,
      items: [
        { icon: 'fas fa-home', title: 'Home', to: '/' },
        { icon: 'fas fa-clipboard-list', title: 'About', to: '/about' },
        { icon: 'fas fa-code', title: 'Services', to: '/services' },
        { icon: 'fas fa-heartbeat', title: 'Swiper', to: '/swiper' }
      ],
      title: 'PRO 1423 Training'
    }
  },
  methods: {
    onScroll () {
      if (typeof window === 'undefined') return
      const top = window.pageYOffset || document.documentElement.offsetTop || 0
      this.fab = top > 20
    },
    toTop () {
      this.$vuetify.goTo(0)
    }
  }
}
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition-property: opacity;
  transition-duration: .25s;
}

.fade-enter-active {
  transition-delay: .25s;
}

.fade-enter, .fade-leave-active {
  opacity: 0
}

</style>
