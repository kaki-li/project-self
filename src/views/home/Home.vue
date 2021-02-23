<template>
  <div id="home">
    <nav-bar class="home-navbar"> <div slot="center">长安引力Uni-T</div></nav-bar>
     <home-swiper :banners='banners'></home-swiper>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar"
import homeSwiper from './childComps/homeswiper' 
import {getHomeMultidata} from "network/home"


// import Swiper from '../../components/common/swiper/Swiper.vue'
// import SwiperItem from '../../components/common/swiper/SwiperItem.vue'
  export default {
    name: "Home",
    components:{
      NavBar,
      homeSwiper
   
    },
    data() {
      return {
        banners:[],
        recommends:[]
      }
    },
    created() {
      // 1请求多个数据
      getHomeMultidata().then(res =>{
        
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;

        

      })
    },
  }
</script>

<style scoped>
  .home-navbar{
    background-color: var(--color-tint);

  }
</style>
