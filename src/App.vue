<template>
  <div class="app-container">
    <Header :title="'购物车案例'"></Header>
    <Goods
      v-for="item in arrs"
      :key="item.id"
      :title="item.goods_name"
      :count="item.goods_price"
      :pic="item.goods_img"
      :status="item.goods_state"
    ></Goods>
    <Footer></Footer>
  </div>
</template>

<script>
import Footer from "@/components/Footer/Footer";
import Goods from "@/components/Goods/Goods";
import Header from "@/components/Header/Header";
import axios from "axios";
export default {
  components: {
    Footer,
    Goods,
    Header,
  },
  data() {
    return {
      arrs: [],
    };
  },
  methods: {
    async initCarData() {
      const { data: res } = await axios.get("https://www.escook.cn/api/cart");
      if (res.status === 200) {
        this.arrs = res.list;
        console.log(this.arrs);
      }
    },
  },
  created() {
    this.initCarData();
  },
};
</script>

<style lang="less" scoped>
.app-container {
  padding-top: 45px;
  padding-bottom: 50px;
}
</style>
