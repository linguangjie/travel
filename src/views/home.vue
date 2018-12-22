<template>
  <div class="page">
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import homeHeader from "../components/home/Header";
import homeSwiper from "../components/home/Swiper";
import homeIcons from "../components/home/Icons";
import homeRecommend from "../components/home/Recommend";
import homeWeekend from "../components/home/Weekend";
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      city: "",
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  mounted() {
    this.getHomeInfo();
  },
  methods: {
    getHomeInfo() {
      axios.get("/mock/index.json").then(res => {
        res = res.data;
        if (res.ret && res.data) {
          const data = res.data;
          this.city = data.city;
          this.swiperList = data.swiperList;
          this.iconList = data.iconList;
          this.recommendList = data.recommendList;
          this.weekendList = data.weekendList;
        }
      });
    }
  },
  components: {
    homeHeader,
    homeSwiper,
    homeIcons,
    homeRecommend,
    homeWeekend
  }
};
</script>

<style scoped>
</style>
