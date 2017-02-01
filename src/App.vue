<template>
  <div>
    <v-header></v-header>
    <div class="tab">
      <div class="tab-item">
        <a v-link="{path:'/goods'}">商品</a>
      </div>
      <div class="tab-item">
        <a v-link="{path:'/ratings'}">评论</a>
      </div>
      <div class="tab-item">
        <a v-link = "{path:'/seller'}">商家</a>
      </div>
    </div>
    <!--刷新路由-->
    <router-view></router-view>
  </div>
</template>

<script>
  import header from './components/header/header.vue';

  export default {
      components: {
        'v-header': header
      }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
    .tab
      display:flex
      background :pink
      width :100%
      height : 40px
      line-height :40px
      .tab-item
        flex :1
        text-align :center
        a
          display : block
          color:rgb(77,85,93)
        a.active
          color:#f40
</style>
