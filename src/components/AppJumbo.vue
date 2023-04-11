<script>
import { store } from '../store.js';


export default {
  name: 'AppJumbo',

  data() {
    return {
      store,

    }
  },

  created() {
    window.addEventListener('scroll', this.elScrollParallax);
  },
  unmounted() {
    window.removeEventListener('scroll', this.elScrollParallax);
  },

  methods: {
    elScrollParallax() {
      let win_pos = window.pageYOffset;


      let img = document.getElementById('img-bg');
      let imgPos = img.getBoundingClientRect();
      console.log(imgPos.top)

      if (win_pos > imgPos.top) {
        img.style.transform = "translateY(" + imgPos.top * -0.5 + "px)"
      }
    }
  }
}
</script>

<template>
  <div class="jumbo-container">
    <!-- Jumbo Top -->
    <div class="top-side">
      <img src="/img/home_slider_bg.jpg" alt="bg" id="img-bg">
      <div class="info-jumbo">
        <h1>Tech Forum!</h1>
        <span>Discuss all the latest technology news and trends</span>
        <div class="btn btn-primary">get avada now!<i class="fa-solid fa-chevron-right"></i> </div>
      </div>
    </div>

    <!-- Jumbo Down -->
    <div class="bottom-side">
      <div class="text-wrapper">

        <h2>Avada Forum is the place to be</h2>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus saepe quasi eveniet aliquam libero,
          doloribus
          similique nam, non inventore a dignissimos cupiditate! Id amet praesentium a ipsum quo dolores laboriosam.</p>
      </div>
    </div>

  </div>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;

.jumbo-container {
  width: 100%;
  height: 110vh;

  .top-side {
    width: 100%;
    height: 70%;

    position: relative;
    overflow: hidden;

    img {
      position: absolute;
      top: 0;
      left: 0;


      width: 110%;
      height: 110%;
      object-fit: cover;
      object-position: 0px 0px;
    }

    .info-jumbo {
      position: relative;
      top: 0;

      max-width: 1000px;
      height: 100%;
      margin: 0 auto;

      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
      gap: 1em;

      h1 {
        font-size: 4.5em;
      }

      .btn {
        margin-top: 1em;
        text-transform: uppercase;
        font-size: .8em;
        font-weight: 600;

        padding: .8em 2em;

        i {
          font-size: .7em;
          padding-left: .5em;
          position: relative;
          left: 0px;
        }

        &:hover {
          padding: 1em 2.2em;

          i {
            font-size: .8em;
            animation: arrow-btn-animation 1.5s infinite
          }
        }

      }
    }
  }

  .bottom-side {
    height: 30%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    padding: 2em 0;
    background: $Color5;
    color: $Color3;

    .text-wrapper {
      max-width: 1000px;
      margin: 1em auto;

      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      h2 {
        text-transform: uppercase;
        font-size: .9em;
        margin: 1em 0;
        margin-bottom: 2em;
        letter-spacing: .4em;
      }

      p {
        font-size: 1.3em;
        color: $Color6;
        text-align: center;
        line-height: 1.7em;
      }
    }
  }

}

// Animazione Freccia Bottone
@keyframes arrow-btn-animation {
  0% {
    left: 0px;
  }

  50% {
    left: 3px;
  }

  100% {
    left: 0px;
  }
}
</style>
