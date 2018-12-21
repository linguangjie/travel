<template>
  <div class="page">
      <home-header></home-header>
      <home-swiper></home-swiper>
      <home-icons></home-icons>
  </div>
</template>

<script>
import homeHeader from '../components/home/Header'
import homeSwiper from '../components/home/Swiper'
import homeIcons from '../components/home/Icons'
export default {
  name: "Home",
  data() {
    return {};
  },
  components: {
      homeHeader,
      homeSwiper,
      homeIcons
  }
};
</script>

<style scoped>
</style>
