<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="(item, index) in recommendList" :key="index">
        <div class="item-img-wrapper">
          <img class="item-img" src>
        </div>
        <div class="item-info">
          <p class="item-title"></p>
          <p class="item-desc"></p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "homeWeekend",
  data() {
    return {
      recommendList: []
    };
  },
  components: {}
};
</script>

<style scoped lang="stylus">
@import '../../assets/styles/mixins.styl';

.recommend-title {
  margin-top: 0.2rem;
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
}

.item-img-wrapper {
  overflow: hidden;
  height: 0;
  padding-bottom: 33.9%;

  .item-img {
    width: 100%;
  }
}

.item-info {
  padding: 0.1rem;

  .item-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    ellipsis();
  }

  .item-desc {
    line-height: 0.4rem;
    color: #ccc;
    ellipsis();
  }
}
</style>
