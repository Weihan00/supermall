<template>
  <div id="home">
    <nav-bar class="home-nav">
      <template v-slot:center><span>购物商场</span></template>
    </nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <feature-view />
    <tab-control
      class="tab-control"
      :titles="['流行', '新款', '精选']"
    ></tab-control>
    <ul>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
      <li>dd</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "../../components/common/navbar/NavBar.vue";
import TabControl from "../../components/content/tabControl/TabControl.vue";
import { getHomeMutilData, getHomeGoodsData } from "../../network/home";
import FeatureView from "./childComps/FeatureView.vue";
import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";

export default {
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        'pop': {page: 0, list: []},
        'news': {page:0, list: []},
        'sell': {page: 0, list: []} 
      }
    };
  },
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl,
  },
  created() {
    getHomeMutilData().then((res) => {
      console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
    getHomeGoodsData('pop', 1).then(res=>{
      console.log(res)
    })
  },
};
</script>


<style scoped>
#home {
  padding-top: 44px;
}

.home-nav {
  background-color: pink;
  color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}

.tab-control {
  position: sticky;
  top: 44px;
}
</style>