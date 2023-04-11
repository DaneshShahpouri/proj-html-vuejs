<script>
import { store } from '../store.js';


export default {
  name: 'AppNavbar',

  data() {
    return {
      store,

      links: ['Home', 'Apple', 'Microsoft', 'Android', 'Forums', 'Contact us'],

      currentPage: 0,
    }
  },

  methods: {
    changePage(index) {
      this.currentPage = index
    }
  }


}
</script>

<template>
  <div class="navbar-container">

    <div class="inner-nav">

      <!-- Logo -->
      <div class="logo-wrapper">
        <img src="/img/logo.png" alt="logo">
      </div>

      <div class="right-side-nav">
        <!-- Links -->
        <ul class="nav-menu">
          <li v-for="(link, index) in links" :class="this.currentPage == index ? 'active' : ''"
            @click="changePage(index)">
            {{ link }}</li>

        </ul>

        <!-- Join -->
        <button class="btn btn-secondary">Join</button>

        <!-- Ricerca -->
        <button class="btn btn-neutro"><i class="fa-solid fa-magnifying-glass"></i></button>


      </div>

    </div>

  </div>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;

.navbar-container {
  width: 100%;
  height: 80px;
  background-color: $Color1;


  .inner-nav {
    height: 100%;
    max-width: 1000px;
    margin: 0 auto;

    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;

    .logo-wrapper {
      padding: 1em;
      height: 100%;

      img {
        height: 100%;
      }
    }

    .right-side-nav {
      height: 100%;
      display: flex;
      flex-flow: row nowrap;
      align-items: center;
      gap: 1em;

      .nav-menu {
        height: 100%;
        display: flex;
        align-items: center;
        gap: 1em;

        list-style-type: none;

        li {
          height: 100%;
          position: relative;
          font-size: .9em;
          display: flex;
          align-items: center;
          color: darken($color: $Color2, $amount: 8);

          cursor: pointer;
          transition: all .2s;

          &:hover {
            text-shadow: 1px 1px 5px rgba(255, 255, 255, 0.6);
            color: $Color2;


          }

          &:active {
            text-shadow: 1px 1px 2px transparent;
          }

          &.active::before {
            content: '';
            display: block;

            position: absolute;
            bottom: -10px;
            left: 50%;
            width: 25px;
            height: 25px;
            rotate: 45deg;
            background-color: $Color1;
            transform: translateX(-50%);
            z-index: 2;
          }
        }
      }
    }
  }

}
</style>
