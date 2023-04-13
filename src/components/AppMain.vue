<script>
import { store } from '../store.js';
import AppMainFirstSection from './AppMainFirstSection.vue';
import AppMainSecondSection from './AppMainSecondSection.vue';

export default {
  name: 'AppMain',

  data() {
    return {
      store,

    }
  },

  components: {
    AppMainFirstSection,
    AppMainSecondSection,
  },
}
</script>

<template>
  <AppMainFirstSection></AppMainFirstSection>
  <AppMainSecondSection></AppMainSecondSection>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;
</style>
