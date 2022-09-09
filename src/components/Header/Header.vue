<template>
  <div class="header-container">{{ titleAs }}</div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "购物车",
      required : true
    },
  },
  data() {
    return {
      titleAs: this.title,
    };
  },
};
</script>

<style lang="less" scoped>
.header-container {
  font-size: 12px;
  height: 45px;
  width: 100%;
  background-color: #1d7bff;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  position: fixed;
  top: 0;
  z-index: 999;
}
</style>
