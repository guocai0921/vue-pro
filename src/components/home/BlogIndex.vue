<template>
  <div class="index_box">
    <blog-header></blog-header>
    <hr/>
    <div>
      这是首页，嘻嘻嘻。
    </div>
    <hr/>
    <blog-footer></blog-footer>
  </div>
</template>

<script>
  import blogHeader from '@/components/common/BlogHeader.vue'
  import blogFooter from '@/components/common/BlogFooter.vue'
  export default {
    name: "BlogIndex",
    components: { blogHeader, blogFooter },
    computed:{
      // 控制中间内容区域的最小高度。如果内容太少，而浏览器窗口太高，
      // 就设置：中间内容区域最小高度 = 窗口高度 - 头部高度 - 底部高度 .
      // 本例子中，头部高度是40px，底部高度是40px，所以减80。
      contentStyle(){
        return {
          padding:0,
          margin: 0,
          border: 0,
          width: "100%",
          height: "auto",
          minHeight: this.$store.getters.rootWindowResizeFlag > -1 ? window.innerHeight - 90 + "px" : 0
        }
      }
    }
  }
</script>

<style lang="css">
  .index_box {
    margin:0;
    padding:0;
    border:0;
  }
</style>
