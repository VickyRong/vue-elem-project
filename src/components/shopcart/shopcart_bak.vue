<template>
  <div class="shopcart">
    <div class="content">
      <div class="content-left">
        <div class="logo-wrapper">
          <div class="logo">
            <i class="icon-shopping_cart"></i>
          </div>
          <div class="num">12</div>
        </div>
        <div class="price" :class="totalPrice">￥{{ totalPrice}}</div>
        <div class="desc">另需配费{{deliveryPrice}}元</div>
      </div>
      <div class="content-right">
        <div class="pay">￥元起送</div>
      </div>
    </div>
  </div>
</template>
<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/styles/mixin.styl";
  @import "shopcart.styl";
</style>

<script type="text/ecmascript-6">
  export default{
    props: {
      selectFoods: {
        type: Array,
        default() {
          return [];
        }
      },
      deliveryPrice: {
        type: Number,
        default: 0
      },
      minPrice: {
        type: Number,
        default: 0
      }
    },
      computed: {
        totalPrice() {
          console.log(1);
          let total = 0;
          this.selectFoods.forEach((food) => {
            total += food.price * food.count;
          });
          return total;
        }
      }

  };
</script>
