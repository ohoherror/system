<template>
  <div>
    <div class="your_scores_container">
      <header class="your_scores">
        <span class="score_num">{{score}}</span>
        <span class="fenshu">分！</span>
      </header>
      <div class="result_tip">{{scoreTips}}</div>
    </div>
    <div class="share_button" @click="showCover"></div>
    <div class="share_code">
      <header class="share_header">关注葡萄之家，获取答案。</header>
      <img src="../../assets/images/4-4.png" height="212" width="212" class="code_img">
    </div>
    <div class="share_cover" v-show="showHide" @click="showCover">
      <img src="../../assets/images/5-2.png" class="share_img">
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "score",
  data() {
    return {
      showHide: false, //是否显示提示
      score: 0, //分数
      scoreTips: "", //分数提示
      rightAnswer: [2, 7, 12, 13, 18], //正确答案
      scoreTipsArr: [
        "你说，是不是把知识都还给小学老师了？",
        "还不错，但还需要继续加油哦！",
        "不要嘚瑟还有进步的空间！",
        "智商离爆表只差一步了！",
        "你也太聪明啦，葡萄之家欢迎你！"
      ]
    };
  },
  computed: mapState(["answerid"]),
  created() {
    this.computedScore();
    this.getScoreTip();
  },
  methods: {
    //计算分数
    computedScore() {
      this.answerid.forEach((item, index) => {
        if (item == this.rightAnswer[index]) {
          this.score += 20;
        }
      });
    },
    //是否显示分享提示
    showCover: function() {
      this.showHide = !this.showHide;
    },
    //根据分数显示提示
    getScoreTip: function() {
      let index = Math.ceil(this.score / 20) - 1;
      this.scoreTips = this.scoreTipsArr[index];
    }
  }
};
</script>

<style lang="scss">
</style>
