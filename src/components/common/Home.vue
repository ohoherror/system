<template>
  <div class="container">
    <head-item></head-item>

    <div>
      <div class="sider">
        <sider-item></sider-item>
      </div>
      <div class="content">
        <div class="content-box" :class="{'content-collapse':collapse}">
          <div>
            <transition name="move" mode="out-in">
              <keep-alive>
                <router-view></router-view>
              </keep-alive>
            </transition>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import headItem from "./headItem";
import siderItem from "../../page/item/siderItem";
export default {
  data() {
    return {
      collapse: false
    };
  },
  components: {
    siderItem,
    headItem
  }
};
</script>

<style lang='scss'>
.container {
  height: 100vh;

  .content {
    margin-top: 80px;
    margin-left: 255px;
  }
}
</style>
