<script>
import { store } from '../store.js';


export default {
  name: 'AppMainFirstSection',

  data() {
    return {
      store,

      cards: [
        {
          title: 'Morbi vitae dui euismod vulputate sollicitudin',
          date: 'October 11th, 2015',
          comments: ['Wow', 'I love it!!'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_25-320x202.jpg',
          img: '/img/post_feat_img_25-700x441.jpg'
        }, {
          title: 'Vivamus pellenteque',
          date: 'October 11th, 2015',
          comments: [],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_24-320x202.jpg',
          img: '/img/post_feat_img_24-700x441.jpg'
        }, {
          title: 'Donec ornare pretium eget scelisque justo',
          date: 'October 11th, 2015',
          comments: ['Great'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_23-320x202.jpg',
          img: '/img/post_feat_img_23-700x441.jpg'
        }, {
          title: 'Fusce sollictudin nunc sed placerat varius',
          date: 'October 11th, 2015',
          comments: ['Wow', 'I love it!!', 'yeah'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_22-320x202.jpg',
          img: '/img/post_feat_img_22-700x441.jpg'
        }, {
          title: 'Donec facilis sodales leo sit amet laorem',
          date: 'October 11th, 2015',
          comments: ['AWWW', 'Ok. no.', 'Fantastique.'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_21-320x202.jpg',
          img: '/img/post_feat_img_21-700x441.jpg'
        }, {
          title: 'Proin eu purus sed aru aliquet curabir vens',
          date: 'October 11th, 2015',
          comments: [],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_20-320x202.jpg',
          img: '/img/post_feat_img_20-700x441.jpg'
        },
      ]

    }
  }
}
</script>

<template>
  <div class="first-section-container">

    <div class="title-wrapper">
      <span>Phasellus eget metus</span>
      <h2>All the latest news</h2>
      <div class="divisor"></div>
    </div>

    <div class="cards-wrapper">

      <div class="card" v-for="(card, index) in cards">

        <div class="img-wrapper">
          <img :src="card.img" alt="">
        </div>

        <div class="text-wrapper">

          <!-- title card -->
          <div class="title">{{ card.title }}</div>

          <!-- data e commenti -->
          <div class="date-comments">
            <div class="date">{{ card.date }} || </div>

            <div v-if="card.comments.length > 0" class="comments">{{ card.comments.length }} Comments </div>
            <div v-else class="comments"> Comments Off</div>

          </div>

          <!-- Descrizione -->
          <span class="descrizione">{{ card.desc }}</span>

        </div>


      </div>

      <div class="preview-square">
        <div class="text-prev-wrapper">
          <span class="title-sec">Featured Article</span>
          <h3>Cras malesuada et orci eget pharetra</h3>
          <span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae quasi exercitationem temporibus. Fuga
            nisi maiores delectus harum beatae, aliquam distinctio suscipit, aspernatur unde eos expedita libero nesciunt
            quam molestiae architecto.</span>
          <div class="btn btn-secondary">Read More<i class="fa-solid fa-chevron-right"></i> </div>
        </div>
      </div>
    </div>

  </div>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;

.first-section-container {
  background-color: $Color2;
  color: $Color3;
  padding: 2em 0;

  .title-wrapper {
    max-width: 1000px;
    margin: 2.5em auto;

    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1.2em;

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

  // Cards---------------
  .cards-wrapper {
    width: 100%;
    max-width: 1000px;
    margin: 0 auto;

    display: flex;
    flex-flow: row wrap;
    gap: 2em;

    .card {
      width: calc((100% / 3) - (2em / 3 * 2));
      display: flex;
      flex-direction: column;
      gap: 1em;

      // Posizione delle cards
      &:nth-child(n+4) {
        order: 3;
      }

      .img-wrapper {

        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }

      .text-wrapper {
        display: flex;
        flex-direction: column;
        gap: .4em;
        padding: .5em 0;
        font-size: .9em;

        .title {
          font-size: 1.2em;
          font-weight: 600;
          color: $Color3;
        }

        .date-comments {
          font-size: .8em;
          color: $Color6;

          display: flex;

          .comments {
            padding-left: .4em;
            font-weight: 600;
          }

        }

        .descrizione {
          color: $Color6;
          font-weight: 100;
        }
      }
    }

    .preview-square {
      max-width: 1000px;
      margin: 2em auto;
      padding: 4.5em;

      order: 2;

      width: 100%;
      height: 500px;

      background-image: url('/img/featured_article_1_bg.jpg');
      background-size: cover;

      .text-prev-wrapper {
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 1em;
        justify-content: end;
        align-items: start;

        color: $Color2;

        .title-sec {
          letter-spacing: .2em;
        }

        h3 {
          font-size: 1.7em;
        }

        span {
          font-size: .9em;
        }

        .btn {
          i {
            font-size: .8em;
            padding-left: .5em;
          }
        }
      }
    }

  }

  // fineCards---------------
}
</style>
