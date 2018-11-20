<template>
  <div class="main-bottom">
    <div class="main-bottom-text">
      LET’S BUILD A LEGEND
    </div>
    <div class="main-bottom-button">
      DROP US A LINE
    </div>
  </div>
</template>

<script>
  export default {
    name: 'siteMainBottom',
  }
</script>

<style lang="scss" scoped>
  $black: #272729;
  $white: #F3F3F4;
  $delay: 0.5s;

  .main-bottom {
    text-align: center;
    margin: 0.6rem auto 0 auto;
    min-height: 220px;
    color: $black;

    .main-bottom-text {
      font-family: "Oswald", "Arial";
      font-size: 0.3rem;
      font-weight: 800;
      transform: scale(1, 1.4);
    }
    .main-bottom-button {
      background: $black;
      width: 1.6rem;
      min-width: 170px;
      line-height: 70px;
      font-size: 0.12rem;
      font-family: "Oswald", "Arial";
      font-weight: 800;
      transform: scale(1, 0.9);
      margin: 0.3rem auto;
      color: white;
      cursor: pointer;
      transition: all $delay;

      &:hover {
        transition: all $delay;
        background: $white;
        color: $black;
      }
    }
  }

</style>
