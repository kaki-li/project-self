<template>
  <div class='nav-bar'>
      <!-- slot中不写class布局yong div 包裹写class -->
      <div class="left">1<slot name="left"></slot></div>
      <!-- 具名插条会被div slot:''替换  -->
      <div class="center"><slot name="center">2</slot></div>
      <div class="right">3<slot name="right"></slot></div>

  </div>
</template>

<script>
export default {
}
</script>

<style  scoped>
    .nav-bar {
        color: seashell;
        display: flex;
        line-height: 44px;
        height: 44px;
        text-align: center;
        box-shadow: 0 1px 1px rgba(100, 100, 100, .1);
    }
   /* 多个类同事选择 */
    .left, .right {
        width:60px;
        

    }

    .center {
        
        flex:3;
      
    }
</style>