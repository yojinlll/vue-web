<template>
  <footer class="site-footer-wrapper">
    <div class="site-footer">
      <div class="footer-content">
        <h2>STAY UP TO DATE</h2>
        <form action="" class="footer-form">
          <input type="text" name="email" placeholder="ENTER YOUR EMAIL" autocomplete="off">
          <button><div></div></button>
        </form>
        <div class="footer-block-grid">
          <div class="grid-1">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-mountains"></use>
            </svg>
          </div>
          <div class="grid-2">
            <p>JOIN THE JOURNEY</p>
            <div>
              <svg class="icon" aria-hidden="true">
                <use xlink:href="#icon-facebook"></use>
              </svg>
              <svg class="icon" aria-hidden="true">
                <use xlink:href="#icon-ins"></use>
              </svg>
            </div>
          </div>
          <div class="grid-3">
            <p>© 2018 NEW LEGEND 4X4</p>
            <p>WEBSITE BY FHOKE</p>
          </div>
        </div>
        <p class="end-text">704 E LINCOLN WAY AMES, IA 50010 USA</p>
      </div>
    </div>
    <div class="site-footer-placeholder"></div>
  </footer>
</template>

<script>
export default {
  name: 'siteFooter',
}
</script>

<style lang="scss" scoped>
  $black: #1C1C1E;
  $delay: 0.3s;
  $color: #4d4d4d;
  .flex{
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .icon {
    width: 4em; height: 4em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }

  .site-footer-wrapper{
    .site-footer{
      position: fixed;
      background: $black;
      height: 520px; width: 100%;
      left: 0; bottom: 0;
      color: white;

      .footer-content{
        width: 92%;
        margin: 0.6rem auto;

        h2{
          margin: 15px 0;
          font-size: 12px; font-weight: 400;
          transform: scale(1,1.2);
          letter-spacing: 4px;
        }

        .footer-form{
          display: flex;
          position: relative;

          input[type="text"]{
            border-bottom: 2px solid $color;
            color: white;
            width: 100%;
            background: $black;
            padding: 10px 0;
            font-size: 0.22rem;
            font-weight: 800;
            transform: scale(1,1.5);
          }
          button{
            border: none;
            position: absolute;
            background: $black;
            height: 40px; width: 40px;
            cursor: pointer;
            right: 0;
            top: 15%;
            transition: all $delay;

            div {
              width: 50%;
              height: 50%;
              position: relative;
              left: 22%;
              top: 23%;

              &:before {
                content: '';
                display: block;
                width: 25px;
                height: 2px;
                background: white;
                position: absolute;
                left: 0px;
                top: 12px;
              }
              &:after {
                content: '';
                display: block;
                border: 5px solid transparent;
                border-left-color: white;
                position: absolute;
                right: -11px;
                top: 8px;
              }
            }
            &:hover{
              transform: scale(1.2, 1.2);
            }
          }
        }

        .footer-block-grid{
          border: 1px solid $color;
          width: 100%; height: 1.2rem;
          margin-top: 0.4rem;
          display: flex;
          p{
            text-align: center; transform: scale(0.8,1.2); font-size: 12px;
            letter-spacing: 4px; font-weight: 600;
            transition: all 1s;
          }

          div{ border: 1px solid $color; flex: 1; }

          .grid-1{ @extend .flex; background: $color; }
          .grid-2{
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;

            p{ margin-top: 0.4rem}
            div{
              border: none;
              flex: 1;
              svg { width: 1.5em; height: 1.5em; margin: 10px;}
            }
          }
          .grid-3{
            @extend .flex;
            flex-direction: column;

            p:last-child{ margin-top: 10px; color: #777777; cursor: pointer;
              &:hover{
                transition: all $delay;
                color: white;
              }
            }
          }

        }

        .end-text{
          color: #777777;
          margin-top: 0.4rem; text-align: center;
          letter-spacing: 2px;
          font-size: 12px;
          transform: scale(1,1.2);
        }
      }

    }
    .site-footer-placeholder{
      background: #c8c8c8;
      height: 520px;
    }
  }

</style>
