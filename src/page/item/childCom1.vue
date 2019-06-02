<template>
  <div>
    <p @click="$listeners.chdata2()">子组件</p>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    coo: String,

    title: String
  }
};
</script>

<style>
</style>
