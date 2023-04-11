<script>
import { store } from '../store.js';
import AppMainFirstSection from './AppMainFirstSection.vue';

export default {
  name: 'AppMain',

  data() {
    return {
      store,

    }
  },

  components: {
    AppMainFirstSection,
  },
}
</script>

<template>
  <AppMainFirstSection></AppMainFirstSection>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;
</style>
