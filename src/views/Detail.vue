<template>
  <div class="page">
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :bannerImgs="gallaryImgs"></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from "../components/detail/Banner";
import DetailHeader from "../components/detail/Header";
import DetailList from "../components/detail/List";
import axios from "axios";
export default {
  name: "Detail",
  data() {
    return {
      sightName: "",
      bannerImg: "",
      gallaryImgs: [],
      list: []
    };
  },
  methods: {
    getDetailInfo() {
      axios
        .get("/mock/detail.json?id=", {
          params: {
            id: this.$route.params.id
          }
        })
        .then(res => {
          res = res.data;
          if (res.ret && res.data) {
            const data = res.data;
            this.sightName = data.sightName;
            this.bannerImg = data.bannerImg;
            this.gallaryImgs = data.gallaryImgs;
            this.list = data.categoryList;
          }
        });
    }
  },
  mounted() {
    this.getDetailInfo();
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  }
};
</script>

<style scoped lang="stylus">
.content {
  height: 50rem;
}
</style>
