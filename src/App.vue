<template>
  <div id="app">
    <md-app class="md-scrollbar" md-waterfall md-mode="fixed">
      <md-app-toolbar class="md-primary animated fadeInRight" md-elevation="0">
        <md-button class="md-icon-button pointer" @click="toggleMenu" v-if="!menuVisible">
          <md-icon>menu</md-icon>
        </md-button>
        <h3 class="md-title pointer" style="flex: 1"><router-link to="/"><span class="logoColor">MedFind</span></router-link></h3>
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible" md-persistent="full" md-elevation="5">
        <md-toolbar class="md-transparent" md-elevation="0">
          <span>Navigation</span>

          <div class="md-toolbar-section-end">
            <md-button class="md-icon-button md-dense" @click="toggleMenu">
              <md-icon>keyboard_arrow_left</md-icon>
            </md-button>
          </div>
        </md-toolbar>

        <md-list>
          <router-link to="/">
            <md-list-item @click="mobileMenu" class="pointer">
              <md-icon>home</md-icon>
              <span class="md-list-item-text">Home</span>
            </md-list-item>
          </router-link>

          <router-link to="/UserGuide">
           <md-list-item @click="mobileMenu" class="pointer">
              <md-icon>help_outline</md-icon>
              <span class="md-list-item-text">User Guide</span>
            </md-list-item>
          </router-link>
        </md-list>
      </md-app-drawer>
      <md-app-content style="padding: 0px; margin: 0px; height; 600px;">
        <router-view></router-view>
        <md-button class="md-fab md-fab-bottom-right md-accent animated bounceIn">
          <md-icon>person</md-icon>
        </md-button>
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: () => ({
    menuVisible: true
  }),
  methods: {
    toggleMenu () {
      this.menuVisible = !this.menuVisible
    },
    mobileMenu () {
      var width = window.innerWidth
      if (width < 600) {
        this.menuVisible = false
      }
    },
    registerCompo () {
      alert('register')
    },
    loginCompo () {
      alert('login')
    }
  },
  beforeMount: function () {
    this.mobileMenu()
  }
}
</script>

<style lang="scss">
  .md-app {
    font-family: 'Quicksand', sans-serif;
    min-height: 700px;  
    overflow: auto;
    border: 2px solid rgba(#000, .12);
  }
  
   // Demo purposes only
  .md-drawer {
    width: 230px;
    max-width: calc(100vw - 125px);
  }
  .pointer{
    cursor: pointer;
  }

  .logoColor{
    color: #fff;
  }
</style>
