<template>
  <header class="header-wrapper">
    <div class="header-inside">
      <div class="header-icon">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-mountains"></use>
        </svg>
      </div>

      <!--改 js 控制-->
      <div class="header-sidebar-icon" @click="sidebarToggle">
        <div class="bar bar-down"></div>
        <div class="bar"></div>
        <div class="bar bar-up"></div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'siteHeader',
  inject: ['eventBus'],
  methods: {
    sidebarToggle(){
      this.eventBus.$emit('sidebarToggle')

    }
  }
}
</script>

<style lang="scss" scoped>
  $color: white;
  $delay: 0.3s;

  .icon {
    width: 3em; height: 3em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }

  .header-wrapper{
    display: flex;
    justify-content: center;

    .header-inside{
      width: 97%;
      display: flex;
      justify-content: space-between;
      align-items: center;

      .header-icon{
        height: 100%; width: 120px;
        margin: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
      }
      .header-sidebar-icon{
        display: flex;
        height: 20px;
        flex-direction: column;
        justify-content: center;
        position: relative;
        cursor: pointer;

        .bar{
          position: relative;
          width: 20px; height: 2px;
          background: $color;
        }
        .bar-down{
          background: $color;
          position: absolute;
          top: 0px;
          transition: all $delay;
        }
        .bar-up{
          background: $color;
          position: absolute;
          bottom: 0px;
          transition: all $delay;
        }
        &:hover{
          .bar-down{
            transition: all $delay;
            transform: translateY(9px);
          }
          .bar-up{
            transition: all $delay;
            transform: translateY(-9px);
          }
        }
      }
    }
  }
</style>
