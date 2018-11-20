<template>
  <div class="site-slide-item">
    <p class="price">{{item.price}}</p>
    <h2 class="name">{{item.name}}</h2>
    <ul class="item-list">
      <li>
        <div>
          <p>engine</p>
          <p>{{item.engine}}</p>
        </div>
      </li>
      <li>
        <div>
        <p>color</p>
        <p>{{item.color}}</p>
        </div>
      </li>
      <li>
        <div>
        <p>style</p>
        <p>{{item.style}}</p>
        </div>
      </li>
      <li>
        <div>
        <p>gearbox</p>
        <p>{{item.gearbox}}</p>
        </div>
      </li>
    </ul>




  </div>
</template>

<script>
export default {
  name: 'siteSlideItem',
  props: {
    item: Object,
  },
}
</script>

<style lang="scss" scoped>
  $black: #1C1C1E;

  .site-slide-item{
    margin: 20px 0;
    height: 90%;
    font-family: "Oswald","Arial",sans-serif;

    .price{
      line-height: 20px;
      padding: 20px 30px 0.1rem 30px;
      color: $black;
      font-size: 0.15rem;
      letter-spacing: 2px;
    }

    .name{
      text-transform: uppercase;
      font-size: 0.22rem;
      transform: scale(1,1.5);
      padding: 20px 60px 0.1rem 30px;
      font-weight: 800;

    }

    .item-list{
      padding: 20px 30px 0.1rem 30px;
      display: flex;
      flex-wrap: wrap;

      li{
        width: 50%;
        margin: 10px 0;


        div{
          height: 100%;
          margin-right: 30px;
          padding-bottom: 15px;
          border-bottom: 2px solid #cacaca;

          p:nth-child(1){
            text-transform: uppercase;
            margin-bottom: 10px;
            font-size: 12px;
            font-weight: 600;
            transform: scale(1,1.4);
            letter-spacing: 3px;
            color: #47474a;
          }
          p:nth-child(2){
            color: #78787b;
          }
        }
      }
    }
  }
</style>
