<template>
  <div id="app">
    <div class="container">
      <!-- header -->
      <app-header />
      <!-- menu -->
      <app-menu @navigate="currentView = $event" />
      <!-- content -->
      <main>
        <component :is="currentView" />
      </main>
    </div>
  </div>
</template>

<script>
import './styles/global.scss'
import AppHeader from './components/AppHeader'
import AppMenu from './components/AppMenu'
import Home from './views/Home.vue'
import Mixin from './views/Mixin.vue'
import About from './views/About.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMenu,
    Home,
    Mixin,
    About
  },
  data() {
    return {
      currentView: 'Home'
    };
  }
}
</script>

<style lang="scss">
.container {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
  padding: 2rem;
}
</style>
