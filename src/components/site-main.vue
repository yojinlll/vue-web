<template>
  <main class="main-wrapper" ref="wrapper">
    <slot name="main-top"></slot>
    <slot name="main-middle"></slot>
    <slot name="main-bottom"></slot>
  </main>
</template>

<script>
  export default {
    name: 'siteMain',
  }
</script>

<style lang="scss" scoped>
  $color: black;
  $delay: 0.3s;

  .main-wrapper {
    margin: 60px auto 0 auto;
    width: 92%;
    position: relative;
    /*z-index: 1;*/

  }

</style>
