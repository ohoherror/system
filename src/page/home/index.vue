<template>
  <div class="app">
    <div class="sider">
      <sider-item></sider-item>
    </div>
    <div>
      <div></div>
    </div>
  </div>
</template>

<script>
import siderItem from "../item/siderItem";
export default {
  data() {
    return {};
  },
  components: {
    siderItem
  }
};
</script>

<style lang='scss'>
.sider {
  width: 300px;
}
</style>
