<script>
import { store } from './store.js';
import AppNavbar from './components/AppNavbar.vue';
import AppJumbo from './components/AppJumbo.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  data() {
    return {
      store,

    }
  },

  components: {
    AppNavbar,
    AppJumbo,
    AppMain,
    AppFooter,
  },

  methods: {

  }
}

</script>

<template>
  <div class="main-container">
    <AppNavbar class="navbar"></AppNavbar>
    <AppJumbo class="jumbo"></AppJumbo>
    <AppMain></AppMain>
    <AppFooter></AppFooter>

  </div>
</template>

<style lang= "scss" scoped>
@use './scss/variables' as *;

.navbar {
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
  z-index: 2;
  position: fixed;
}

.jumbo {
  padding-top: 70px;
}
</style>
