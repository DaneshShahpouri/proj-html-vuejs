<script>
import { store } from '../store.js';


export default {
  name: 'AppMainSecondSection',

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

      // Elementi con scroll
      let img = document.getElementById('img-banner');

      //Posizione degli elementi
      let imgPos = img.getBoundingClientRect();


      if (win_pos > imgPos.top) {
        img.style.transform = "translateY(" + imgPos.top * -0.3 + "px)"
      };

    },
  },
}
</script>

<template>
  <div class="second-section-container">
    <div class="banner">
      <span>Read Our Blog <i class="fa-solid fa-arrow-right"></i></span>
    </div>


    <div class="selector-wrapper">

      <div class="title-wrapper">
        <span>Phasellus eget metus</span>
        <h2>Forum Section</h2>
        <div class="divisor"></div>
      </div>

      <div class="forum-selector">

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-solid fa-file-lines"></i>
          </div>

          <span class="title-selector">News & Community</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-brands fa-apple"></i>
          </div>

          <span class="title-selector">Apple Forum</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-brands fa-windows"></i>
          </div>

          <span class="title-selector">Microsoft Forum</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-brands fa-android"></i>
          </div>

          <span class="title-selector">Android Forum</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-solid fa-mug-saucer"></i>
          </div>

          <span class="title-selector">General Discussion</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-solid fa-cubes"></i>
          </div>

          <span class="title-selector">App & Software</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-solid fa-laptop"></i>
          </div>

          <span class="title-selector">Gadget & Stuff</span>

        </div>

        <div class="selector">

          <div class="icon-wrapper">
            <i class="fa-solid fa-wrench"></i>
          </div>

          <span class="title-selector">Tutorial & Guide</span>

        </div>

      </div>

    </div>

    <div class="banner">
      <span>Go to our forum <i class="fa-solid fa-arrow-right"></i></span>
    </div>

    <div class="community">
      <div class="community-banner">
        <div class="text-wrapper">
          <h3>Hey! Join to our Community</h3>
          <span>Nulla molestie tortor nec lectus venenatis, sed blandt dui finibus. Curabitur feugiat vulputate purus
            ipsums dolores ficilis uns etra.</span>
          <button class="btn btn-primary">Sing up <i class="fa-solid fa-chevron-right"></i></button>
        </div>

        <img src="/img/join_now_cta_bg.jpg" alt="" id="img-banner">
      </div>

      <div class="sub-newsletter">

        <div class="newsletter-inner">

          <h5>Subscribe to our Newsletter</h5>

          <div class="input-wrapper">
            <input type="email" placeholder="Insert your Email*">
            <button class="btn btn-secondary"> Send</button>

          </div>

        </div>

      </div>

    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;

.banner {
  width: 100%;
  background: $Color3;
  text-align: center;
  padding: 2em 0;


  span {

    cursor: pointer;

    i {
      font-size: .8em;
    }
  }
}

.selector-wrapper {
  background: $Color5;

  .title-wrapper {
    max-width: 1000px;
    padding: 6em 0 2em 0;
    margin: 0 auto;

    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.2em;

    color: $Color3;

    span {
      font-size: 1.1em;
      letter-spacing: .2em;
      font-weight: 500;
      color: $Color6;
    }

    h2 {
      font-weight: 800;
      font-size: 2em;
    }

    .divisor {
      width: 50px;
      height: 2px;
      background: $Color4;
    }

  }

  .forum-selector {
    max-width: 1000px;
    margin: 0 auto;
    padding: 4.5em 0 8em 0;

    display: flex;
    flex-flow: row wrap;
    gap: 2.5em;

    .selector {
      width: calc((100% / 4) - (2.5em / 4 * 3));
      aspect-ratio: 1/1;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      background: $Color2;
      border-top: 2px solid $Color1;
      box-shadow: 2px 2px 5px rgba(0, 0, 0, 0);
      cursor: pointer;
      transition: all .4s;


      .icon-wrapper {
        background: $Color4;
        width: 100px;
        height: 100px;
        border-radius: 50%;
        margin-bottom: 1em;

        position: relative;
        transition: all .4s;

        i {
          font-size: 2.5em;
          color: $Color2;
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translateX(-50%) translateY(-50%);
        }
      }

      .title-selector {
        color: $Color3;
        font-weight: 600;
        font-size: 1em;
        transition: all 1s;
      }
    }

    .selector:hover {
      box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.164);

      .icon-wrapper {
        scale: 1.05;

        i {

          animation: hover 1s;
        }

      }

      .title-selector {
        letter-spacing: 1px;
      }
    }
  }
}

.community {
  width: 100%;


  .community-banner {
    position: relative;

    width: 100%;
    height: 450px;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;

    img {
      position: absolute;

      width: 120%;
      opacity: .9;
    }

    .text-wrapper {
      position: relative;
      z-index: 1;
      width: 45%;
      height: 100%;
      display: flex;
      flex-flow: column;
      gap: 2em;
      justify-content: center;
      align-items: center;

      h3 {
        font-size: 4em;
        text-align: center;
        text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.709);
      }

      span {
        text-align: center;
        text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.509);
      }
    }

  }

  .sub-newsletter {

    background: $Color5;

    .newsletter-inner {
      margin: 0 auto;
      max-width: 1000px;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-flow: column;
      gap: 1.5em;
      padding: 4em 0;

      h5 {
        font-size: 1.3em;
        font-weight: 200;
        color: $Color3;
      }

      .input-wrapper {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;


        input {
          width: 60%;
          padding: 0.8em;
          border: 0;
          background: $Color2;
          color: $Color3;
        }

        .btn {
          width: 20%;
          margin-left: 1em;
        }
      }
    }
  }

}

@keyframes hover {
  0% {
    left: 50%;
    scale: 1;
  }

  50% {
    left: 52%;
    top: 48%;
    rotate: -10deg;
    scale: 1
  }


  100% {
    left: 50%;
    scale: 1;
  }

}
</style>
