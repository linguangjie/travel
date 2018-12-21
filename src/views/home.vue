<template>
  <div class="page">
      <home-header></home-header>
      <home-swiper></home-swiper>
  </div>
</template>

<script>
import homeHeader from '../components/home/Header'
import HomeSwiper from '../components/home/Swiper'
export default {
  name: "Home",
  data() {
    return {};
  },
  components: {
      homeHeader,
      HomeSwiper
  }
};
</script>

<style scoped>
</style>
