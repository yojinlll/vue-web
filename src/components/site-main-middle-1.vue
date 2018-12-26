<template>
  <div class="main-middle-1" >
    <div class="middle1-wrapper">
      <div class="middle1-text">
        <h2>TELL A BETTER STORY</h2>
        <p>
          When you think about it, most cars on
          the road today are invisible.
          Camouflaged in a sea of white, black
          and silver metal, with nothing to say.
          Then there are cars that stand out.
          Start conversations. Have a story to tell.
          The ones that bring back old
          memories and make new ones. But
          often they come with problems, kinks,
          and just don’t keep us on the move.
          That’s where we come in…
        </p>
        <div class="text-button">OUR STORY</div>
      </div>
      <div class="middle1-slide-wrapper">
        <ul class="slide-list" :style="{transform: move}">
          <li class="slide-item item-1" ref="firstItem">
            <div class="item-pic"></div>
            <div class="item-text">
              <slot name="item-1"></slot>
            </div>
          </li>
          <li class="slide-item item-2">
            <div class="item-pic"></div>
            <div class="item-text">
              <slot name="item-2"></slot>
            </div>
          </li>
          <li class="slide-item item-3">
            <div class="item-pic"></div>
            <div class="item-text">
              <slot name="item-3"></slot>
            </div>
          </li>
          <li class="slide-item item-4">
            <div class="item-pic"></div>
            <div class="item-text">
              <slot name="item-4"></slot>
            </div>
          </li>
          <li class="slide-item item-5" ref="lastItem">
            <div class="item-pic"></div>
            <div class="item-text">
              <slot name="item-5"></slot>
            </div>
          </li>
        </ul>
        <div class="middle1-control">
          <div class="slide-control">
            <div class="prev-item" @click="prev()" :class="{notAllow: notAllow === 1}">
              <div></div>
            </div>
            <div class="next-item" @click="next()" :class="{notAllow: notAllow === 2}">
              <div></div>
            </div>
          </div>
          <div class="button">ALL BUILDS</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'siteMainMiddle1',
    data(){
      return {
        move: undefined,
        distance: 0,
        firstItemLeft: 0,
        lastItemLeft: 0,
        prevButtonLeft: 0,
        notAllow: 1,
      }
    },
    methods: {
      prev(){
        this.firstItemLeft = this.$refs.firstItem.getBoundingClientRect().left
        this.lastItemLeft = this.$refs.lastItem.getBoundingClientRect().left

        if (this.firstItemLeft > 0) {
          this.distance = 0
          this.notAllow = 1
        }else {
          this.notAllow = 0
          this.distance = this.distance - (this.$refs.firstItem.getBoundingClientRect().width + 50)
          this.move = `translateX(-${this.distance}px)`
        }
      },
      next(){
        this.firstItemLeft = this.$refs.firstItem.getBoundingClientRect().left
        this.lastItemLeft = this.$refs.lastItem.getBoundingClientRect().left

        if (this.lastItemLeft < this.$refs.firstItem.getBoundingClientRect().width) {
          this.notAllow = 2
          return
        }
        this.notAllow = 0
        this.distance = this.distance + (this.$refs.firstItem.getBoundingClientRect().width + 50)
        this.move = `translate(-${this.distance}px)`
      }
    }
  }
</script>

<style lang="scss" scoped>
  $black: #1C1C1E;
  $itemPicHeight: 2.2rem;
  $delay: 0.5s;

  .main-middle-1 {
    background: url("../assets/img/main-middle-1.jpg") no-repeat center;
    background-size: cover;
    /*min-height: 1700px;*/

    .middle1-wrapper {
      background: rgba(28, 28, 30, 0.7);
      height: 1700px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: flex-end;
      overflow: hidden;

      .middle1-text {
        padding: 200px 50px 0 0;
        width: 50%;
        right: 50px;
        color: white;

        h2 {
          color: #f1f1f1;
          font-weight: 400; font-size: 15px;
          transform: scale(1, 1.4); letter-spacing: 3px;
        }
        p {
          margin-top: 0.4rem; color: #b6b6b6;
          font-size: 25px; font-weight: 200;
        }
        .text-button {
          margin-top: 40px;
          font-weight: 600; color: #f1f1f1;
          transform: scale(1, 0.8);
          transition: all $delay;
          cursor: pointer;

          &:hover{
            transition: all $delay;
            transform: scale(1,1.2);
          }
        }
      }
      .middle1-slide-wrapper {
        background: #E8E8E8;
        height: 37%; width: 100%;
        min-height: 650px;
        position: relative;

        .slide-list {
          margin-left: 5%;
          display: flex;
          position: absolute;
          top: -2.2rem;
          transition: all $delay;

          .slide-item {
            height: 5.5rem; width: 3.3rem;
            min-height: 704px;
            min-width: 400px;
            margin-right: 50px;
            display: flex;
            flex-direction: column;
            cursor: pointer;
            transition: all $delay;

            .item-pic { height: $itemPicHeight; transition: all $delay; }
            .item-text { flex: 1; background: white; transition: all $delay; }

            &:hover {
              .item-text { transition: all $delay; background: #F3F3F4;}
            }

          }
        }

        .middle1-control {
          width: 90%;
          position: absolute;
          left: 5%;
          bottom: 0.6rem;
          display: flex;
          justify-content: space-between;

          .slide-control {
            min-width: 200px; min-height: 50px;
            display: flex;
            justify-content: space-between;
            cursor: pointer;

            .prev-item {
              width: 49%;
              height: 100%;
              background: white;
              position: relative;

              div {
                width: 50%;
                height: 50%;
                position: relative;
                left: 22%;
                top: 23%;
                transition: all $delay;

                &:before {
                  content: '';
                  display: block;
                  border: 5px solid transparent;
                  border-right-color: $black;
                  position: absolute;
                  left: 10px;
                  top: 8px;
                }
                &:after {
                  content: '';
                  display: block;
                  width: 30px;
                  height: 2px;
                  background: $black;
                  position: absolute;
                  left: 20px;
                  top: 12px;
                }

              }

              &:hover {
                transition: all $delay;
                background: $black;
                div {
                  &:before {
                    border-right-color: white;
                  }
                  &:after {
                    background: white;
                  }
                }
              }
            }
            .next-item {
              width: 49%;
              height: 100%;
              background: white;
              position: relative;

              div {
                width: 50%;
                height: 50%;
                position: relative;
                left: 22%;
                top: 23%;
                transition: all $delay;

                &:before {
                  content: '';
                  display: block;
                  width: 30px;
                  height: 2px;
                  background: $black;
                  position: absolute;
                  left: 9px;
                  top: 12px;
                }
                &:after {
                  content: '';
                  display: block;
                  border: 5px solid transparent;
                  border-left-color: $black;
                  position: absolute;
                  right: 0px;
                  top: 8px;
                }
              }
              &:hover {
                transition: all 0.3s;
                background: $black;
                div {
                  &:before {
                    background: white;
                  }
                  &:after {
                    border-left-color: white;
                  }
                }
              }
            }
            .notAllow {
              background: #f2f2f2;
            }
          }
          .button {
            padding: 10px 30px;
            line-height: 30px;
            background: $black;
            color: white;
            font-weight: 800;
            cursor: pointer;
            transition: all $delay;

            &:hover {
              transition: all $delay;
              background: #F3F3F4;
              color: $black;
            }
          }
        }
      }
    }
  }

  /* 轮播单项样式 */
  .slide-list {
    $delay: 0.5s;
    @mixin hidden-pic{
        content: '';
        display: block;
        width: 100%;
        height: 100%;
        visibility: hidden;
    }


    .item-1 {
      .item-pic {
        background: url("../assets/img/slideItem-1-1.jpg") no-repeat center;
        background-size: cover;

        &::after{
          background: url("../assets/img/slideItem-1-2.jpg");
          @include hidden-pic;
        }
      }

      &:hover {
        .item-pic {
          transition: all $delay;
          background: url("../assets/img/slideItem-1-2.jpg") no-repeat center;
          background-size: cover;
        }
      }
    }
    .item-2 {

      .item-pic {
        background: url("../assets/img/slideItem-2-1.jpg") no-repeat center;
        background-size: cover;

        &::after{
          @include hidden-pic;
          background: url("../assets/img/slideItem-2-2.jpg");
        }
      }

      &:hover {
        .item-pic {
          transition: all $delay;
          background: url("../assets/img/slideItem-2-2.jpg") no-repeat center;
          background-size: cover;
        }
      }
    }
    .item-3 {

      .item-pic {
        background: url("../assets/img/slideItem-3-1.jpg") no-repeat center;
        background-size: cover;

        &::after{
          @include hidden-pic;
          background: url("../assets/img/slideItem-3-2.jpg");
        }
      }

      &:hover {
        .item-pic {
          transition: all $delay;
          background: url("../assets/img/slideItem-3-2.jpg") no-repeat center;
          background-size: cover;
        }
      }
    }
    .item-4 {

      .item-pic {
        background: url("../assets/img/slideItem-4-1.jpg") no-repeat center;
        background-size: cover;

        &::after{
          @include hidden-pic;
          background: url("../assets/img/slideItem-4-2.jpg");
        }
      }

      &:hover {
        .item-pic {
          transition: all $delay;
          background: url("../assets/img/slideItem-4-2.jpg") no-repeat center;
          background-size: cover;
        }
      }
    }
    .item-5 {

      .item-pic {
        background: url("../assets/img/slideItem-5-1.jpg") no-repeat center;
        background-size: cover;


        &::after{
          @include hidden-pic;
          background: url("../assets/img/slideItem-5-2.jpg");
        }
      }

      &:hover {
        .item-pic {
          transition: all $delay;
          background: url("../assets/img/slideItem-5-2.jpg") no-repeat center;
          background-size: cover;
        }
      }
    }

  }

</style>
