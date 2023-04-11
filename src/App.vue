<script>
import { store } from './store.js';
import AppNavbar from './components/AppNavbar.vue';

export default {
  data() {
    return {
      store,

    }
  },

  components: {
    AppNavbar,
  },
}

</script>

<template>
  <div class="main-container">
    <AppNavbar></AppNavbar>
  </div>
</template>

<style lang= "scss" scoped>
@use './scss/variables' as *;
</style>
