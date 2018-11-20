<template>
  <div class="site-aloft">
    <!--<p></p>-->
    <!--<div class="aloft-sidebar-icon">-->
      <!--<div class="bar bar-down"></div>-->
      <!--<div class="bar"></div>-->
      <!--<div class="bar bar-up"></div>-->
    <!--</div>-->
    <slot name="banner"></slot>
    <slot name="main"></slot>
  </div>
</template>

<script>
export default {
  name: 'siteAloft',

}
</script>

<style lang="scss" scoped>
  $color: black;
  $delay: 0.3s;

  .site-aloft{
    background: white;
    position: relative;
    z-index: 1;


  }

</style>
