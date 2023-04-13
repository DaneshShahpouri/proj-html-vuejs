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
          img: '/img/post_feat_img_25-700x441.jpg',
          tutorial: false
        }, {
          title: 'Vivamus pellenteque',
          date: 'October 11th, 2015',
          comments: [],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_24-320x202.jpg',
          img: '/img/post_feat_img_24-700x441.jpg',
          tutorial: false
        }, {
          title: 'Donec ornare pretium eget scelisque justo',
          date: 'October 11th, 2015',
          comments: ['Great'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_23-320x202.jpg',
          img: '/img/post_feat_img_23-700x441.jpg',
          tutorial: true
        }, {
          title: 'Fusce sollictudin nunc sed placerat varius',
          date: 'October 11th, 2015',
          comments: ['Wow', 'I love it!!', 'yeah'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_22-320x202.jpg',
          img: '/img/post_feat_img_22-700x441.jpg',
          tutorial: true
        }, {
          title: 'Donec facilis sodales leo sit amet laorem',
          date: 'October 11th, 2015',
          comments: ['AWWW', 'Ok. no.', 'Fantastique.'],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_21-320x202.jpg',
          img: '/img/post_feat_img_21-700x441.jpg',
          tutorial: false
        }, {
          title: 'Proin eu purus sed aru aliquet curabir vens',
          date: 'October 11th, 2015',
          comments: [],
          desc: 'Donec finibus sit amet orci eget ultricies. Present posuere ante ut erat frigilla, vestibulum placerat metus mattis. Aenean dictum vitae nisl.',
          imgPrev: '/img/post_feat_img_20-320x202.jpg',
          img: '/img/post_feat_img_20-700x441.jpg',
          tutorial: true
        },
      ],

    }
  },

  methods: {

    tutorialArrayMaker() {
      for (let i = 0; i < this.cards.length; i++) {
        if (this.cards[i].tutorial) {
          this.store.tutorialArray.push(this.cards[i])
        }
      }
    },

    elScrollParallax() {
      let win_pos = window.pageYOffset;


      // Elementi con scroll
      let cards = document.querySelectorAll('.card');
      let thumbs = document.querySelectorAll('.thumbnail');
      //console.log(thumb)

      //console.log(cards)

      cards.forEach((card, index) => {
        let cardPos = card.getBoundingClientRect();



        //console.log('index ' + index % 3)
        if (index % 3 == 0) {
          //card 1
          if (cardPos.top < 700) {
            card.classList.add('onfocus')
          }

          // } else if (cardPos.top > 700) {
          //   card.classList.remove('onfocus')
          // }
        } else if (index % 3 == 1) {
          setTimeout(
            () => {
              if (cardPos.top < 700) {
                card.classList.add('onfocus')
              }
              // } else if (cardPos.top > 700) {
              //   card.classList.remove('onfocus')
              // }
            }, 250
          )
        } else if (index % 3 == 2) {
          setTimeout(
            () => {
              if (cardPos.top < 700) {
                card.classList.add('onfocus')
              }
              // } else if (cardPos.top > 700) {
              //   card.classList.remove('onfocus')
              // }
            }, 500
          )
        }

      });

      thumbs.forEach(thumb => {
        let thumbPos = thumb.getBoundingClientRect();


        if (thumbPos.top < 700) {
          thumb.classList.add('onfocus')
        }
      });

    }
  },

  created() {
    window.addEventListener('scroll', this.elScrollParallax);
    this.tutorialArrayMaker()

  },
  unmounted() {
    window.removeEventListener('scroll', this.elScrollParallax);
  },


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

      <!-- Preview Centrale -->
      <div class="preview-square center-square">
        <div class="text-prev-wrapper">
          <span class="title-sec">Featured Article</span>
          <h3>Cras malesuada et orci eget pharetra</h3>
          <span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae quasi exercitationem temporibus. Fuga
            nisi maiores delectus harum beatae, aliquam distinctio suscipit, aspernatur unde eos expedita libero nesciunt
            quam molestiae architecto.</span>
          <div class="btn btn-secondary">Read More<i class="fa-solid fa-chevron-right"></i> </div>
        </div>
      </div>

      <!-- Tutorial e guide -->
      <div class="tutorial-guide">

        <div class="preview-square">
          <div class="text-prev-wrapper">
            <span class="title-sec">Reviewed Product</span>
            <h3>Mauris viverra atisan ipsum eget felis primis efficitur varius</h3>
            <span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae quasi exercitationem temporibus. Fuga
              nisi maiores delectus harum beatae, aliquam distinctio suscipit, aspernatur unde eos expedita libero
              nesciunt
              quam molestiae architecto.</span>
            <div class="btn btn-secondary">Read More<i class="fa-solid fa-chevron-right"></i> </div>
          </div>
        </div>

        <div class="left-side">
          <h4>Tutorial & Guide</h4>
          <div class="divisor"></div>

          <div class="thumbnails" id="thumbnails">
            <div v-for="(card) in this.store.tutorialArray" class="thumbnail">
              <div class="img-wrapper" v-if="card.tutorial">
                <img :src="card.img" alt="anteprima">
              </div>

              <div class="text" v-if="card.tutorial">
                <div class="title">{{ card.title }}</div>

                <div class="date-comment">
                  <div class="date">{{ card.date }} </div>
                  <div class="comments" v-if="card.comments.length > 0">|| {{ card.comments.length }} Comments</div>
                  <div class="comments" v-else>Comments OFF</div>
                </div>
              </div>

            </div>

          </div>
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
  padding: 3em 0 8em 0;

  .title-wrapper {
    max-width: 1000px;
    margin: 2.5em auto;

    padding-bottom: 3em;

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


  }

  .divisor {
    width: 50px;
    height: 2px;
    background: $Color4;
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
      opacity: 0;
      border-bottom: 1px solid rgba(0, 0, 0, 0);
      position: relative;

      &:hover {
        filter: contrast(1.2) saturate(1.1);
        border-bottom: 1px solid $Color4;

        &::after {
          content: '';
          display: block;
          position: absolute;
          bottom: 0;


          width: 200px;
          height: 2px;
          background: $Color4;

          animation: selectArticles 1s;
        }

        img {
          scale: 1.01;
        }

        .text-wrapper {
          font-size: .9em;


          .title {
            font-size: 1.20em;
            color: $Color4;
          }
        }
      }

      // Posizione delle cards
      &:nth-child(n+4) {
        order: 2;
      }

      &.onfocus {
        animation: cardsappears 4s;
        opacity: 1;
      }


      .img-wrapper {

        img {
          width: 100%;
          height: 100%;
          object-fit: cover;

          transition: all .2s;
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

    .tutorial-guide {
      order: 3;

      display: flex;
      height: 100%;
      max-width: 1000px;
      padding: 3em 0;

      .preview-square {
        background-image: url('/img/featured_article_2_bg.jpg');
        background-size: cover;
        height: 400px;

        width: 60%;
      }

      .left-side {
        width: 40%;
        overflow-x: hidden;
        padding: 0 1em;

        &:hover {
          .thumbnails {


            .thumbnail {
              opacity: .5;

              &.onfocus {
                opacity: .5;
              }

              &:hover {
                opacity: 1;
              }

              &:hover {
                opacity: 1;

                .text {
                  .title {
                    color: $Color4;
                  }
                }
              }
            }

          }
        }

        h4 {
          font-size: 1.5em;
          padding-bottom: 1em;
        }

        .thumbnails {
          display: flex;
          flex-direction: column;
          gap: 1em;
          width: 100%;
          padding: 2em 0;


          .thumbnail {
            display: flex;
            align-items: center;
            gap: .5em;
            transition: all .4s;

            opacity: 0;

            &.onfocus {

              animation: appearsthumb .4s;
              opacity: 1;
            }



            .img-wrapper {
              width: 100px;
              height: 90px;
              overflow: hidden;

              img {
                width: 100%;
                height: 100%;
                object-fit: cover;
              }

            }

            .text {
              display: flex;
              flex-direction: column;
              gap: .5em;

              .title {
                font-weight: 600;
                transition: all .3s;
              }

              .date-comment {
                display: flex;
                gap: .5em;
                font-size: .8em;
              }
            }

          }

        }
      }
    }

    .center-square {
      background-image: url('/img/featured_article_1_bg.jpg');
      background-size: cover;

      padding: 2em 0;

      width: 100%;
      max-width: 1000px;
      margin: 2em auto;

      order: 1;

    }

    .preview-square {
      padding: 4.5em;

      height: 500px;


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
          text-transform: uppercase;
          font-size: .70em;
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

@keyframes cardsappears {

  0% {
    opacity: 0;
    margin-top: -3em;
  }

  70% {
    opacity: 1;
    margin-top: 0em;
  }

  75% {
    opacity: 1;
    margin-top: 0em;
    ;
  }

  100% {
    opacity: 1;
    margin-top: 0em;
  }
}

@keyframes selectArticles {
  0% {
    width: 200px;
  }

  25% {
    width: 170px;
  }

  100% {
    widows: 200px;
  }

}

@keyframes appearsthumb {
  0% {
    opacity: 0;
    margin-left: 4em;
  }

  100% {
    opacity: 1;
    margin-left: 0em;
  }
}
</style>
