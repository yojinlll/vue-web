<template>
  <div class="main-top">
    <div class="top-pic top-pic-left">
      <div class="top-content">
        <h2>LEGEND SERIES</h2>
        <h5>COMPLETE SPEC BUILDS</h5>
      </div>
    </div>
    <div class="top-pic top-pic-right">
      <div class="top-content">
        <h2>RUNNER SERIES</h2>
        <h5>CLASSIC RETRO - MODS</h5>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'siteMainTop',
  data(){
    return {
      styleLeft: {
        backgroundImage: "url('http://pihkjsl6o.bkt.clouddn.com/top-pic-left-1.jpg')",
      }
    }
  },
}
</script>

<style lang="scss" scoped>
  $delay: 0.5s;
  $h1Color: #1C1C1E;

  .main-top{
    display: flex;

    .top-pic{
      z-index: 1;
      margin-bottom: 20px;
      height: 2rem;
      flex-grow: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      text-align: center;
      cursor: pointer;
      transition: all $delay;
      &:hover{
        h2{ transition: all $delay; transform: translateY(15px); }
        h5{ transition: all 0s; transform: translateY(40px); opacity: 0; }
      }

      .top-content{
        background: white;
        padding: 0.3rem 0.5rem;
        color: $h1Color;
        font-size: 0.23rem;
        position: absolute;
        top: 1.4rem;
        transition: all $delay;
        z-index: 1;
        opacity: 1;

        h5{letter-spacing: 2px; font-weight: 400; font-size: 0.12rem; color: #5d5d5d; margin-top: 10px}
        h2,h5{ transition: all $delay; }
      }
    }


    .top-pic-left{
      margin-right: 10px;
      background: url("../assets/img/top-pic-left-1.jpg") no-repeat;
      background-size: cover;

      &::after{
        content: '';
        display: block;
        width: 100%;
        height: 100%;
        background: url("../assets/img/top-pic-left-2.jpg");
        visibility: hidden;
      }

      &:hover{
        transition: all $delay;
        background: url("../assets/img/top-pic-left-2.jpg");
        background-size: cover;

        .top-content{ background: #E8E8E8; }
      }
    }
    .top-pic-right{
      margin-left: 10px;
      background: url("../assets/img/top-pic-right-1.jpg") no-repeat;
      background-size: cover;

      &::after{
        content: '';
        display: block;
        width: 100%;
        height: 100%;
        background: url("../assets/img/top-pic-right-2.jpg");
        visibility: hidden;
      }

      &:hover{
        transition: all $delay;
        background: url("../assets/img/top-pic-right-2.jpg") no-repeat;
        background-size: cover;
        .top-content{ background: #E8E8E8; }
      }
    }
  }

</style>
