<template>
  <aside class="site-sidebar" :class="{active: isActive, animation: isActive}">
    <div class="header-sidebar-icon">
      <div class="sidebar-icon">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-jianshu"></use>
        </svg>
      </div>
      <div class="sidebar-icon">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-github"></use>
        </svg>
      </div>
      <div class="sidebar-icon sidebar-close" @click="sidebarClose">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-x"></use>
        </svg>
      </div>
    </div>
    <ul class="sidebar-menu">
      <li class="menu-item">
        <a href="#">builds</a>
      </li>
      <li class="menu-item">
        <a href="#">story</a>
      </li>
      <li class="menu-item">
        <a href="#">process</a>
      </li>
      <li class="menu-item">
        <a href="#">team</a>
      </li>
      <li class="menu-item">
        <a href="#">ledger</a>
      </li>
      <li class="menu-item">
        <a href="#">contact</a>
      </li>
    </ul>
  </aside>
</template>

<script>
  import '../assets/svg'


  export default {
    name: 'siteSidebar',
    inject: ['eventBus'],
    data(){
      return {
        isActive: false,
      }
    },
    methods: {
      sidebarClose(){
        this.isActive = false
      }
    },
    mounted(){
      this.eventBus.$on('sidebarToggle', () => {
        this.isActive = true
      })
    },
  }
</script>

<style lang="scss" scoped>
  $black: #1C1C1E;
  $delay: 0.5s;

  .icon {
    width: 1.5em; height: 1.5em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }

  .site-sidebar {
    background: white;
    height: 100vh;
    width: 600px;
    position: fixed;
    z-index: 2;
    right: 0;
    transition: all $delay;
    transform: translateX(600px);

    .header-sidebar-icon {
      height: 50px;
      display: flex;
      justify-content: flex-end;

      .sidebar-icon {
        display: flex;
        justify-content: center; align-items: center;
        width: 50px; height: 50px;
        cursor: pointer;
      }

      .sidebar-close {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 50px;height: 50px;
        transition: all 0.2s;

        &:hover {
          transition: all 0.2s;
          transform: scale(0.6, 0.6);
        }
      }
    }
    .sidebar-menu {
      text-align: end;
      margin-top: 20px;

      .menu-item {
        padding: 15px;
        font-size: 35px;
        font-weight: 800;
        font-family: "Oswald", "Arial";
        text-transform: uppercase;
        transform: scale(1, 1.3);

        a {color: #CECECE; transition: all $delay;}

        a:hover {
          transition: all $delay;
          color: $black;
        }
      }
    }
  }

  .active {
    transform: translateX(0);
  }

  .animation {
    .menu-item:nth-child(1) {
      animation: menuMove 1s;
      opacity: 1;
    }
    .menu-item:nth-child(2) {
      animation: menuMove 1.2s;

    }
    .menu-item:nth-child(3) {
      animation: menuMove 1.3s;
    }
    .menu-item:nth-child(4) {
      animation: menuMove 1.4s;

    }
    .menu-item:nth-child(5) {
      animation: menuMove 1.5s;

    }
    .menu-item:nth-child(6) {
      animation: menuMove 1.6s;
    }

    @keyframes menuMove {
      0% { transform: translateX(400px) scale(1, 1.3); opacity: 0}
      100% { transform: translateX(0) scale(1, 1.3); opacity: 1;}
    }
  }

</style>
