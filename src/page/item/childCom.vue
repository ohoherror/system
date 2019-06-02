<template>
  <div>
    <p @click="$listeners.chdata2()">子组件</p>
  </div>
</template>

<script>
import childCom1 from "./childCom1";
export default {
  data() {
    return {};
  },

  props: {
    boo: String
  },
  inheritAttrs: false,

  created() {
    console.log(this.$attrs); // { "boo": "Html", "coo": "CSS", "doo": "Vue", "title": "前端工匠" }
  },

  components: { childCom1 }
};
</script>

<style>
</style>
