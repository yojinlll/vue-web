<template>
  <div id="app">
    <div>
      <site-aloft>
        <site-banner slot="banner">
          <site-header></site-header>
        </site-banner>

        <site-main slot="main">
          <site-main-top slot="main-top"></site-main-top>

          <site-main-middle slot="main-middle">
            <site-main-middle-1 slot="middle-1">

              <site-slide-item slot="item-1" :item="item1"></site-slide-item>
              <site-slide-item slot="item-2" :item="item2"></site-slide-item>
              <site-slide-item slot="item-3" :item="item3"></site-slide-item>
              <site-slide-item slot="item-4" :item="item4"></site-slide-item>
              <site-slide-item slot="item-5" :item="item5"></site-slide-item>

            </site-main-middle-1>

            <site-main-middle-2 slot="middle-2"></site-main-middle-2>
            <site-main-middle-3 slot="middle-3"></site-main-middle-3>
          </site-main-middle>

          <site-main-bottom slot="main-bottom"></site-main-bottom>
        </site-main>
      </site-aloft>
      <site-footer></site-footer>
    </div>
    <site-sidebar></site-sidebar>
  </div>
</template>

<script>
  import Vue from 'vue'
  import Header from './components/site-header'
  import Banner from './components/site-banner'
  import Main from './components/site-main'
  import MainTop from './components/site-main-top'
  import MainMiddle from './components/site-main-middle'
  import MainMiddle1 from './components/site-main-middle-1'
  import MainMiddle2 from './components/site-main-middle-2'
  import MainMiddle3 from './components/site-main-middle-3'
  import MainBottom from './components/site-main-bottom'
  import Footer from './components/site-footer'
  import SlideItem from './components/site-slide-item'
  import Aloft from './components/site-aloft'
  import Sidebar from './components/site-sidebar'

  export default {
    name: 'App',
    components: {
      'site-header': Header,
      'site-banner': Banner,
      'site-main': Main,
      'site-main-top': MainTop,
      'site-main-middle': MainMiddle,
      'site-main-middle-1': MainMiddle1,
      'site-main-middle-2': MainMiddle2,
      'site-main-middle-3': MainMiddle3,
      'site-main-bottom': MainBottom,
      'site-footer': Footer,
      'site-slide-item': SlideItem,
      'site-aloft': Aloft,
      'site-sidebar': Sidebar,
    },
    data(){
      return {
        eventBus: new Vue (),

        item1: {
          price: '$165,000',
          name: 'LSii-One',
          engine: '6,2L LS3(430hp)',
          color: 'Ceylon Green x Creme Brûlée Top',
          style: 'Scout II',
          gearbox: '6 Speed Automatic'
        },
        item2: {
          price: '$64,000',
          name: '’69 Copper Mountain',
          engine: '5.3 Gen III LS (300hp)',
          color: 'Original Patina Copper Paint - 2282',
          style: 'Scout 800',
          gearbox: '4 Speed 4L60e Automatic'
        },
        item3: {
          price: '$165,000',
          name: 'LSii-Five',
          engine: '6.2L L96 (360hp)',
          color: 'Mayan Mist',
          style: 'Scout II',
          gearbox: '6 Speed Automatic'
        },
        item4: {
          price: '$67,000',
          name: '‘72 Sunrise – Iron & Resin',
          engine: '5.3 Gen II LS (300hp)',
          color: 'Sunrise Yellow',
          style: '1972 Scout II',
          gearbox: '4l60, 4 Speed Automatic'
        },
        item5: {
          price: '$175,000',
          name: 'LSii-Two',
          engine: '6.2 LSA (600hp)',
          color: 'Magnetic Gray',
          style: 'Scout II',
          gearbox: '6 Speed Automatic'
        },
      }
    },
    provide () {
      return {
        eventBus: this.eventBus
      }
    },
    methods: {
      setRem(){
        let pageWidth = window.innerWidth
        document.documentElement.style.fontSize = pageWidth / 10 + 'px'
      },
    },
    created(){
      this.setRem()
      window.onresize = this.setRem
    }
  }
</script>

<style lang="scss">
  /*init*/
  * {margin: 0; padding: 0;}

  * {box-sizing: border-box}

  *::after {box-sizing: border-box}

  *::before {box-sizing: border-box}

  ul, ol {list-style: none}

  a {text-decoration: none;}

  input {border: none; outline: none;}

  body {
    font-size: 16px;

    #app{ display: flex; }
  }
</style>
