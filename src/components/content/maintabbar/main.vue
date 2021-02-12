<template>
  <tab-bar>
    <tab-bar-item path="/home" >
      <!--dom 中使用路径需要用 ~ 来识别配置的别名-->
      <template v-slot:item-icon><img  src="../../../assets/img/tabbar/home.svg" alt=""></template>
      <template v-slot:item-icon-active><img src="../../../assets/img/tabbar/home_active.svg" alt=""></template>
      <template v-slot:item-text>首页</template>
    </tab-bar-item>
    <tab-bar-item path="/category">
      <template v-slot:item-icon><img src="../../../assets/img/tabbar/category.svg" alt=""></template>
      <template v-slot:item-icon-active><img src="../../../assets/img/tabbar/category_active.svg" alt=""></template>
      <template v-slot:item-text><div>品类</div></template>
    </tab-bar-item>
    <tab-bar-item path="/cart">
      <template v-slot:item-icon><img src="../../../assets/img/tabbar/shopcart.svg" alt=""></template>
      <template v-slot:item-icon-active><img src="../../../assets/img/tabbar/shopcart_active.svg" alt=""></template>
      <template v-slot:item-text><div>购物车</div></template>
    </tab-bar-item>
    <tab-bar-item path="/me">
     <template v-slot:item-icon><img src="../../../assets/img/tabbar/profile.svg" alt=""></template>
      <template v-slot:item-icon-active><img src="../../../assets/img/tabbar/profile_active.svg" alt=""></template>
     <template v-slot:item-text> <div >我的</div></template>
    </tab-bar-item>
  </tab-bar>
</template>

<script>
export default {
    name :MainTabBar,
    components: {
        TabBar, TabBarItem
    }
}
</script>