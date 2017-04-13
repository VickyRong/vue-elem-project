<template>
   <div v-show="showFlag" class="food" transition="move">
       我是food组件
   </div>
</template>
<style lang="stylus" rel="stylesheet/stylus">
     @import "../../common/styles/mixin.styl";
     @import "food.styl";
</style>
<script type="text/ecmascript-6">
    export default {
        props: {
            food: {
                type: Object
            }
        },
        data() {
            return {
                showFlag: false
            };
        },
        methods: {
           show() {
               this.showFlag = true;
           }
        }
    };
</script>
