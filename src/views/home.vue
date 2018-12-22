<template>
  <div class="page">
      <home-header></home-header>
      <home-swiper></home-swiper>
      <home-icons></home-icons>
      <home-recommend></home-recommend>
      <home-weekend></home-weekend>
  </div>
</template>

<script>
import homeHeader from '../components/home/Header'
import homeSwiper from '../components/home/Swiper'
import homeIcons from '../components/home/Icons'
import homeRecommend from '../components/home/Recommend'
import homeWeekend from '../components/home/Weekend'
export default {
  name: "Home",
  data() {
    return {};
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
