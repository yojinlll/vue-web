<template>
  <div class="main-middle-3">
    <div class="middle3-wrapper">
      <div class="middle3-banner"></div>
      <div class="middle3-instagram-wrapper">
        <div class="middle3-instagram">
          <div class="instagram-left-part"></div>
          <div class="instagram-right-part">
            <div class="instagram-right-1"></div>
            <div class="instagram-right-2"></div>
            <div class="instagram-right-3"></div>
            <div class="instagram-right-4"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'siteMainMiddle3',
  }
</script>

<style lang="scss" scoped>
  $delay: 0.5s;

  .main-middle-3 {
    height: 8.5rem;

    .middle3-wrapper {
      height: 100%;
      display: flex;
      flex-direction: column;

      .middle3-banner {
        height: 65%;
        background: url("http://pihkjsl6o.bkt.clouddn.com/middle3-banner.jpg") no-repeat center;
        background-size: cover;
      }
      .middle3-instagram-wrapper {
        display: flex;
        justify-content: center;
        flex: 1;
        position: relative;

        .middle3-instagram {
          background: white;
          height: 145%;
          width: 92%;
          position: absolute;
          bottom: 0;
          display: flex;
          justify-content: space-between;
          padding: 0.15rem;

          .instagram-left-part {
            background: url("http://pihkjsl6o.bkt.clouddn.com/instagram-left-part.jpg") no-repeat center;
            background-size: cover;
            width: calc(50% - 0.15rem / 2);
            position: relative;
            cursor: pointer;
            transition: all $delay;

            &:before {
              content: '';
              display: block;
              width: 100%;
              height: 100%;
              position: absolute;
              background-color: rgba(46, 46, 46, 0.32);
              transition: all $delay;
            }

            &:hover {
              &:before {
                content: '';
                display: block;
                width: 100%;
                height: 100%;
                position: absolute;
                background-color: rgba(46, 46, 46, 0.5);
                transition: all $delay;
              }
            }
          }
          .instagram-right-part {
            width: calc(50% - 0.15rem / 2);
            display: flex;
            justify-content: space-between;
            align-content: space-between;
            flex-wrap: wrap;

            div {
              width: calc(50% - 0.15rem / 2);
              height: calc(50% - 0.15rem / 2);
            }
            .instagram-right-1 {
              @extend .instagram-left-part;
              background: url("http://pihkjsl6o.bkt.clouddn.com/instagram-right-part-1.jpg") no-repeat center;
              background-size: cover;
              &:before { background-color: rgba(255, 255, 255, 0);}
            }
            .instagram-right-2 {
              @extend .instagram-left-part;
              background: url("http://pihkjsl6o.bkt.clouddn.com/instagram-right-part-2.jpg") no-repeat center;
              background-size: cover;
              &:before { background-color: rgba(255, 255, 255, 0);}
            }
            .instagram-right-3 {
              @extend .instagram-left-part;
              background: url("http://pihkjsl6o.bkt.clouddn.com/instagram-right-part-3.jpg") no-repeat center;
              background-size: cover;
              &:before { background-color: rgba(255, 255, 255, 0);}
            }
            .instagram-right-4 {
              @extend .instagram-left-part;
              background: url("http://pihkjsl6o.bkt.clouddn.com/instagram-right-part-4.jpg") no-repeat center;
              background-size: cover;
              &:before { background-color: rgba(255, 255, 255, 0);}
            }
          }
        }
      }
    }

  }

</style>
