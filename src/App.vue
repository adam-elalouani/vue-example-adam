<script>
import Header from './components/Header.vue'
// TODO: remove
import Home from './components/pages/Home.vue'
import News from './components/pages/News.vue'
import Footer from './components/Footer.vue'
import AboutUs from './components/pages/AboutUs.vue'
import Matches from './components/pages/Matches.vue'
import Cartitem from './components/Footer.vue'
import Cart from './components/Cart.vue'
// hi y'all, going to number the changes (there are 4) so it's clear to you. 
// 1. create a routes object with all your navbar routes
// see https://vuejs.org/guide/scaling-up/routing.html#simple-routing-from-scratch
const routes = {
  '/': Home,
  '/news': News,
  '/about': AboutUs,
  '/cart': Cart
}
export default {
  data() {
    // 2. change the currentPath to be the value of the routes variable (instead of just a string
    return {
      currentPath: routes['/']
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = routes[window.location.hash.slice(1)];
    });
  },
  components: {
    Header,
    News,
    Footer,
    AboutUs,
    Matches,
    Cartitem,
    Cart,
  }
}
</script>

<template>
  <Header />
  <!-- 4. change this to be a dynamic component, and add :is="currentPath" as a directive -->
  <component :is="currentPath" />
  <Footer />
</template>

<style></style>
