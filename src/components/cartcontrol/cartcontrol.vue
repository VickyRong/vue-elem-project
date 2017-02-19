<template>
  <div class="cartcontrol">
    <div class="cart-decrease " v-show="food.count>0" @click="desCart" transition="move">
      <div class="inner icon-remove_circle_outline"></div>
    </div>
    <div class="cart-count" v-show="food.count>0">{{food.count}}</div>
    <div class="cart-add icon-add_circle" @click="addCart"></div>
  </div>
</template>
<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/styles/mixin.styl";
  @import "cartcontrol.styl";
</style>
<script type="text/ecmascript-6">
  import Vue from 'vue';
  export default {
    props: {
      food: {
        type: Object
      }
    },
    methods: {
      addCart(event) { // 加
        if (!event._constructed) { //  防止pc端派发两次事件
          return;
        }
        if (!this.food.count) {
          Vue.set(this.food, 'count', 1); // 调用Vue去设置新的属性，这样才能被观察到
        } else {
          this.food.count++;
        }
        this.$dispatch('cart.add', event.target);
      },
      desCart() { // 减
        if (this.food.count) {
          this.food.count--;    // 当food.count等于0时，减号自动会消失了
        }
      }
    }
  };
</script>
