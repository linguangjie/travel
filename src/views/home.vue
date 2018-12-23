<template>
  <div class="page">
    <home-header></home-header>
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
import { mapState } from "vuex";
export default {
  name: "Home",
  data() {
    return {
      lastCity: "",
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  mounted() {
    this.lastCity = this.city;
    this.getHomeInfo();
  },
  computed: {
    ...mapState(["city"])
  },
  methods: {
    getHomeInfo() {
      axios.get("/mock/index.json?city=" + this.city).then(res => {
        res = res.data;
        if (res.ret && res.data) {
          const data = res.data;
          this.swiperList = data.swiperList;
          this.iconList = data.iconList;
          this.recommendList = data.recommendList;
          this.weekendList = data.weekendList;
        }
      });
    }
  },
  activated() {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city;
      this.getHomeInfo();
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
