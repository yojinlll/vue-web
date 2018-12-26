<template>
  <div class="banner-wrapper" ref="wrapper">
    <div class="banner">
      <slot></slot>

      <div class="banner-content">
        <h2>{{h2}}</h2>
        <h1>{{h1}}</h1>
        <div class="video-button">
          <a href="#">PLAY VIDEO</a>
        </div>
      </div>

      <div class="banner-arrow" @click="scrollY"></div>
    </div>
    <video muted="" autoplay="" loop="" preload="" playsinline="">
      <source src="https://www.newlegend4x4.com/wp-content/themes/new-legend/assets/vid/banner.webm" type="video/webm">
      <source src="https://www.newlegend4x4.com/wp-content/themes/new-legend/assets/vid/banner.ogv" type="video/ogv">
      <source src="https://www.newlegend4x4.com/wp-content/themes/new-legend/assets/vid/banner.mp4" type="video/mp4">
    </video>
  </div>
</template>

<script>
export default {
  name: 'siteBanner',
  data(){
    return {
      h2: 'LEGENDS NEVER DIE',
      h1: 'NEW LEGEND 4X4'
    }
  },
  methods:{
    scrollY(){
      console.log(this.$refs.wrapper.offsetHeight)
      let targetTop = this.$refs.wrapper.offsetHeight
      let n = 25		                                    //一共动多少次（25帧）
      let duration = 400 / n 		                        //多少时间动一次
      let currentTop = window.scrollY
      let distance = ( targetTop - currentTop ) / n
      let i = 0
      let id = setInterval( () => {
        if( i === n ){
          window.clearInterval(id)
          return
        }
        i = i + 1
        window.scrollTo( 0, currentTop + distance * i )
      }, duration)
    }
  }
}
</script>

<style lang="scss" scoped>
  $delay: 0.3s;

  .banner-wrapper{
    min-height: 100vh;
    background: url("../assets/img/banner-video-still.jpg")  no-repeat center;
    background-size: cover;

    video{
      width: 100%;
      height: 100vh;
      display: block;
      object-fit: fill;
      position: absolute;
      left: 0;
      top: 0;
    }

    .banner{
      position: relative;
      height: 100vh;
      /*min-height: 600px;*/
      background: rgba(28,28,30,0.3);
      z-index: 2;

      .banner-content{
        height: 300px;
        margin: 220px 0 0 50px;
        color: white;
        text-align: left;
        h2{ font-family: sans-serif,"Montserrat","Arial"; font-weight: 200; font-size: 20px; letter-spacing: 6px;}
        h1{ font-family: sans-serif,"Oswald","Arial"; font-size: 88px; font-weight: 800; letter-spacing:-4px; transform: scale(1,1.2); margin: 30px 0;}

        .video-button{
          width: 170px;
          margin-top: 30px;
          line-height: 14px;
          padding: 17px 28px;
          background: white;
          outline: none;
          display: flex;
          font-size: 16px;
          cursor: pointer;
          transition: all $delay;

          a{color:  #1C1C1E; font-family: sans-serif,"Montserrat","Arial"; font-weight: 900;}

          &:before{
            content: '';
            display: block;
            border: 7px solid transparent;
            border-left-color: black;
          }
          &:hover{
            transition: all $delay;
            background: #1C1C1E;
            a{color:  white;}
            &:before{ border-left-color: white;}
          }
        }
      }
      .banner-arrow{
        width: 40px; height: 70px;
        position: absolute;
        right: 20px; bottom: 20px;
        display: flex;
        flex-direction: column;
        justify-content: center; align-items: center;
        cursor: pointer;
        transition: all $delay;

        &:before{
          content: '';
          display: block;
          width: 2px; height: 25px;
          background: white;
          transition: all $delay;
        }
        &:after{
          content: '';
          display: block;
          border: 6px solid transparent;
          border-top-color: white;
          transition: all $delay;
        }

        &:hover{
          &:before,&:after{
            transition: all $delay;
            transform: translateY(10px);
            border-top-color: #B5B9B6;
          }
          &:before{ background: #B5B9B6; }
          &:after{ border-top-color: #B5B9B6; }

        }
      }
    }
  }



</style>
