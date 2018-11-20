<template>
  <div class="main-middle-2">
    <div class="middle2-wrapper">
      <div class="next-button" @click="prevItem">
        <div></div>
      </div>
      <p>IN THE</p>
      <p>PRESS</p>
      <div class="prev-button" @click="nextItem">
        <div></div>
      </div>
    </div>
    <div class="middle2-main">
      <ul>
        <li :class="{show:show === 0}">
          <p>"SCOUTS ARE MAKING A COMEBACK, WITH CUSTOMIZERS LIKE NEW LEGEND TAKING THE OLD SCOUTS FROM THE SCRAP HEAP
            AND BRINGING THEM UP FOR THE PRESENT MOMENT."</p>
          <h2>1HICONSUMPTION</h2>
          <h4>Staff Post</h4>
        </li>
        <li :class="{show:show === 1}">
          <p>"NEW LEGEND 4×4 TAKES CLASSIC OFFROADERS AND TURNS THEM INTO INCREDIBLE MODERN MACHINES. ITS LATEST
            “RUNNER” SERIES AIMS TO KEEP THAT CLASSIC PATINA WHILE OFFERING A CONTEMPORARY DRIVING EXPERIENCE."</p>
          <h2>2GEAR JUNKIE</h2>
          <h4>Staff Post</h4>
        </li>
        <li :class="{show:show === 2}">
          <p>"A QUALITY, REBUILT SCOUT IS A BREATH OF FOUR-BY-FOUR FRESH AIR. AND NEW LEGEND 4×4 IS QUICKLY BECOMING THE
            BEST OUTLET FOR RESTO-MODDED INTERNATIONAL SCOUTS."</p>
          <h2>3GEAR PATROL </h2>
          <h4>Staff Post</h4>
        </li>
        <li :class="{show:show === 3}">
          <p>"NEW LEGEND 4×4 TAKES CLASSIC OFFROADERS AND TURNS THEM INTO INCREDIBLE MODERN MACHINES. ITS LATEST
            “RUNNER” SERIES AIMS TO KEEP THAT CLASSIC PATINA WHILE OFFERING A CONTEMPORARY DRIVING EXPERIENCE."</p>
          <h2>4IRON & RESIN</h2>
          <h4>Staff Post</h4>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'siteMainMiddle1',
    data(){
      return {
        // isActive: true,
        show: 0
      }
    },
    methods: {
      prevItem(){
        this.show = (this.show + 1)%4
        console.log(this.show, 'prev')
      },
      nextItem(){
        console.log('prev')
        if(this.show - 1 < 0){
          this.show = 4
          this.show = (this.show - 1)%4
        }else{
          this.show = (this.show - 1)%4
          console.log(this.show, 'next')
        }
      }
    }

  }
</script>

<style lang="scss" scoped>
  $black: #1C1C1E;
  $delay: 0.2s;

  .main-middle-2 {
    position: relative;
    margin-top: 100px;

    .middle2-wrapper {
      height: 3.8rem;
      text-align: center;
      line-height: 1.4rem;
      font-family: "Montserrat", "Arial", sans-serif;
      font-size: 1.3rem; font-weight: 900;
      letter-spacing: 30px;
      color: rgba(90, 90, 90, 0.05);
      padding-top: 0.2rem;
      position: relative;

      .prev-button {
        width: 100px; height: 50px;
        position: absolute;
        top: calc(50% - 25px);
        background: $black;
        cursor: pointer;
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
            border: 5px solid transparent;
            border-right-color: white;
            position: absolute;
            left: 10px;
            top: 8px;
          }
          &:after {
            content: '';
            display: block;
            width: 30px;
            height: 2px;
            background: white;
            position: absolute;
            left: 20px;
            top: 12px;
          }
        }
        &:hover {
          transition: all $delay;
          background: #F3F3F4;
          div {
            &:before {
              border-right-color: $black;
            }
            &:after {
              background: $black;
            }
          }
        }
      }
      .next-button {
        width: 100px; height: 50px;
        position: absolute;
        top: calc(50% - 25px);
        right: 0;
        background: $black;
        cursor: pointer;
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
            width: 30px;
            height: 2px;
            background: white;
            position: absolute;
            left: 10px;
            top: 12px;
          }
          &:after {
            content: '';
            display: block;
            border: 5px solid transparent;
            border-left-color: white;
            position: absolute;
            right: 0px;
            top: 8px;
          }
        }
        &:hover {
          transition: all $delay;
          background: #F3F3F4;
          div {
            &:before {
              background: $black;
            }
            &:after {
              border-left-color: $black;
            }
          }
        }
      }
    }
    .middle2-main {
      color: $black;
      position: absolute;
      width: 60%; height: 100%;
      top: 0; left: 1.8rem;

      ul {
        width: 100%; height: 100%;
        position: relative;

        li {
          display: none;
          position: absolute;
          width: 100%;
          margin: 0.6rem auto;
          text-align: center;
          font-family: "Microsoft YaHei UI";

          p {
            font-size: 0.25rem;
            font-weight: 400;
            margin: 10px;
          }
          h2 {
            margin: 0.5rem 0 10px 0;
            font-size: 0.15rem;
            font-weight: 800;
          }
          h4 {
            color: #6C6C6C;
            font-size: 0.15rem; font-weight: 100;
            letter-spacing: 2px;
          }

        }

        .show {
          display: block;
          animation: showListItem 1s;
        }

        @keyframes showListItem {
          0% {opacity: 0; transform: translateY(40px);}
          100% {opacity: 1; transform: translateY(0);}
        }
      }
    }
  }
</style>
