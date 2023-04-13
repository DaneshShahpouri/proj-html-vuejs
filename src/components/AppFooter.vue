<script>
import { store } from '../store.js';


export default {
  name: 'AppFooter',

  data() {
    return {
      store,

      infoFooter: [
        {
          title: 'Avada Tech Forum',
          content: 'Sed semper, nisl id feugiat eleifend, erat est digssim felis, quis auctor elit enim nec ante. Cras et nibh risus. Pellestesque non mi sit amet mi intermentum',
          question: [],
        }, {
          title: 'Popular Topics',
          content: '',
          question: [
            {
              quest: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse interdum mauris eget gravida tempus. Quisque accumsan vitae metus nec vestibulum. Vestibulum dolor leo, blandit et orci in?',
              answer: 'Nulla eleifend arcu et lectus dictum, a ullamcorper ante sagittis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus',
              open: false,
              close: true,
            }, {
              quest: 'Nunc maximus neque lacus, at porttitor nisl placerat sit amet. Nulla nulla metus, blandit vitae turpis quis, pulvinar lobortis nisi. Aenean sodales massa eu purus viverra, vel laoreet nibh volutpat. In sit amet ligula velit?',
              answer: 'Maecenas efficitur dapibus nulla id gravida. Nam ut tristique justo. Sed pulvinar nisi dolor.',
              open: false,
              close: true,
            }, {
              quest: 'Maecenas in fringilla purus. Donec consequat ut leo non porta. Integer et magna eget arcu efficitur ornare et a felis?',
              answer: 'nec eleifend dui laoreet sit amet. Morbi fringilla turpis non odio rutrum, eget sagittis lorem sodales.',
              open: false,
              close: true,
            }, {
              quest: 'Praesent massa lacus, posuere ac sapien a, bibendum mattis tellus. Aliquam sed felis vehicula, sodales leo ac, aliquam urna. Nam nec dui quis augue elementum laoreet sit amet lacinia mi?',
              answer: 'Donec quam velit, mollis sit amet ultricies sit amet, auctor gravida sapien. Vivamus lacus ipsum, condimentum ut congue ut, tincidunt sed enim. Mauris sit amet dolor a felis ornare tincidunt. Vivamus id orci ligula?',
              open: false,
              close: true,
            }
          ]
        }, {
          title: 'Recent Topics',
          content: '',
          question: [
            {
              quest: 'In eget tempor augue. Mauris dignissim posuere arcu, id finibus velit interdum vitae. Nunc finibus a enim non dictum. In eu iaculis eros. Ut eleifend efficitur ipsum sit amet semper. Nullam gravida dui sed nibh ultricies scelerisque?',
              answer: 'Nulla eleifend arcu et lectus dictum, a ullamcorper ante sagittis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus',
              open: false,
              close: true,
            }, {
              quest: 'ullamcorper venenatis lacus. Aliquam venenatis sem est, lacinia aliquet magna facilisis et. Suspendisse sem nibh, sodales nec ullamcorper vitae, sollicitudin sit amet nisi?',
              answer: 'Maecenas efficitur dapibus nulla id gravida. Nam ut tristique justo. Sed pulvinar nisi dolor.',
              open: false,
              close: true,
            }, {
              quest: 'Pellentesque eget eros vitae sem scelerisque malesuada nec nec lorem. Phasellus non eros libero?',
              answer: 'Etiam dapibus nunc non nibh pellentesque, quis interdum erat maximus. Praesent ut eleifend est. Cras malesuada dictum mi a ullamcorper. Cras consequat elit arcu, id volutpat nisi iaculis sit amet.',
              open: false,
              close: true,
            }, {
              quest: 'Praesent massa lacus, posuere ac sapien a, bibendum mattis tellus. Aliquam sed felis vehicula, sodales leo ac, aliquam urna. Nam nec dui quis augue elementum laoreet sit amet lacinia mi?',
              answer: 'Aliquam feugiat condimentum condimentum. Aenean semper tincidunt lobortis. Duis sed purus nec sapien faucibus laoreet.',
              open: false,
              close: true,
            }
          ]
        }, {
          title: 'Latest Topics',
          content: '',
          question: [
            {
              quest: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse interdum mauris eget gravida tempus. Quisque accumsan vitae metus nec vestibulum. Vestibulum dolor leo, blandit et orci in?',
              answer: 'Nulla eleifend arcu et lectus dictum, a ullamcorper ante sagittis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus',
              open: false,
              close: true,
            }, {
              quest: 'Nunc dictum eros elit, a scelerisque erat fringilla ac. Integer vestibulum vestibulum tristique?',
              answer: 'Morbi tempor lectus quis leo pretium ornare non id augue. Nunc accumsan dapibus dui sodales mollis.',
              open: false,
              close: true,
            }, {
              quest: 'Vestibulum vitae felis eu enim gravida blandit vestibulum eu odio. Quisque laoreet, tortor et blandit rutrum, eros sem convallis lectus, in pellentesque est erat non magna?',
              answer: 'nec eleifend dui laoreet sit amet. Morbi fringilla turpis non odio rutrum, eget sagittis lorem sodales.',
              open: false,
              close: true,
            }, {
              quest: 'Praesent massa lacus, posuere ac sapien a, bibendum mattis tellus. Aliquam sed felis vehicula, sodales leo ac, aliquam urna. Nam nec dui quis augue elementum laoreet sit amet lacinia mi?',
              answer: 'Quisque non sapien ipsum. Fusce sagittis finibus ipsum, non rhoncus enim finibus in. In finibus eget lacus ac ultricies. Sed faucibus diam et ornare luctus. Etiam cursus est in tellus malesuada, eu consectetur ligula pulvinar.',
              open: false,
              close: true,
            }
          ]
        },
      ],


    }
  },

  methods: {
    openSum(indexCol, indexAns) {

      if (this.infoFooter[indexCol].question[indexAns].open) {
        this.infoFooter[indexCol].question[indexAns].close = true;
        setTimeout(
          () => {
            this.infoFooter[indexCol].question[indexAns].open = false;
          }, 1000
        )
      } else {
        this.infoFooter[indexCol].question[indexAns].close = false;
        this.infoFooter[indexCol].question[indexAns].open = true;
      }

    },

  }
}
</script>

<template>
  <div class="footer-container">
    <div class="inner-footer">
      <div class="topic-section">

        <div class="col" v-for="(col, indexCol) in infoFooter">

          <div class="col-title">{{ col.title }}</div>

          <div class="col-content" v-if="col.content != ''">{{ col.content }}</div>

          <div class="col-aswer" v-for="(el, indexAns) in col.question" v-if="col.question.length > 0">

            <div class="summary">
              <i class="fa-solid fa-angle-right" :class="el.open ? 'rotate' : ''"></i>
              <div class="question" @click="openSum(indexCol, indexAns)">{{ el.quest }}</div>
            </div>
            <span class="answer" v-show="el.open" :class="el.close ? 'closer' : ''">{{ el.answer
            }}</span>
          </div>

        </div>

      </div>


    </div>
    <div class="bottom-footer">
      <div class="bottom-footer-inner">
        <div class="left-side">
          <p>@Copyrigth 2023 | Avada theme by <span>Danesh Shahpouri</span> | All rigths Reserverd | Power by
            <span>Vue</span>
          </p>
        </div>

        <div class="right-side">
          <div class="icon-wrapper fb">
            <i class="fa-brands fa-facebook"></i>
          </div>

          <div class="icon-wrapper twitter">
            <i class="fa-brands fa-twitter"></i>
          </div>

          <div class="icon-wrapper insta">
            <i class="fa-brands fa-instagram"></i>
          </div>

          <div class="icon-wrapper yt">
            <i class="fa-brands fa-youtube"></i>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../scss/variables' as *;

.footer-container {
  background: $Color2;
  padding-top: 2em;

  .inner-footer {
    max-width: 1000px;
    margin: 0 auto;

    .topic-section {
      width: 100%;
      display: flex;
      padding: 2em 0;

      .col {
        width: calc(100% / 4);
        color: $Color3;
        font-size: .9em;

        .col-title {
          font-weight: 700;
          text-transform: uppercase;
          margin-bottom: 1.7em;
        }

        .col-content {
          padding-right: 2em;
          color: $Color6;
          line-height: 1.5em;
        }

        .col-aswer {
          width: 90%;
          border-bottom: 1px solid rgb(209, 209, 209);
          color: rgb(40, 40, 40);
          padding: 1em 0;
          font-size: .93em;

          .summary {
            margin: .5em 0;
            font-weight: 800;

            .question {
              margin: .5em 0;
            }

            i {
              margin-top: .2em;
              margin-right: .4em;
              font-size: .9em;
              float: left;
              rotate: 0;
              transition: all .5s;
              font-weight: 700;

              &.rotate {
                rotate: 90deg;
              }
            }

          }

          .answer {
            margin: .5em 0;
            display: block;
            color: $Color4;
            max-height: 200px;
            overflow: hidden;

            animation: open 2s;

            &.closer {
              animation: close 1s;
            }

          }
        }
      }
    }

  }

  .bottom-footer {
    width: 100%;
    border-top: 1px solid rgb(206, 206, 206);

    &-inner {
      max-width: 1000px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      padding: 1em 0;
      color: $Color3;

      .left-side {
        font-size: .7em;
        display: flex;
        align-items: center;

        p {
          span {
            font-weight: 600;
          }
        }
      }

      .right-side {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: .5em;

        .icon-wrapper {
          width: 30px;
          height: 30px;
          border-radius: 50%;

          display: flex;
          justify-content: center;
          align-items: center;

          &.fb {
            background: rgb(60, 89, 152);
          }

          &.twitter {
            background: rgb(84, 172, 238);
          }

          &.insta {
            background: rgb(63, 114, 155);
          }

          &.yt {
            background: rgb(205, 32, 31);
          }

          i {
            color: white;
            font-size: .7em;
            position: absolute;

          }
        }
      }
    }
  }
}

@keyframes open {
  0% {
    max-height: 0px;
    opacity: 0;
  }

  100% {
    max-height: 200px;
    opacity: 1;
  }
}

@keyframes close {
  0% {
    max-height: 200px;
    opacity: 1;
  }

  100% {
    max-height: 0px;
    opacity: 0;
  }
}
</style>
