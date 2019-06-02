<template>
  <div class="deshboard">
    <el-row>
      <el-col :span="8">
        <el-card class="card_one">
          <div class="card_baseinfo">
            <img src="../../assets/img/img.jpg" alt>
            <span>
              <p style="color:#222;font-size:30px">admin</p>
              <p style="color:#999;font-size:14px">超级管理员</p>
            </span>
          </div>
          <div class="card_detatilinfo">
            <span>
              上次登录时间：
              <span>2018-01-01</span>
            </span>
            <span>
              上次登录地点：
              <span>东莞</span>
            </span>
          </div>
        </el-card>
      </el-col>
      <el-col :span="16">bbb</el-col>
    </el-row>
    <el-row>
      <el-col :span="12">
        <div class="visited" id="myChart"></div>
      </el-col>
      <el-col :span="12"></el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.getElementById("myChart"));
      // 绘制图表
      myChart.setOption({
        title: { text: "在Vue中使用echarts" },
        tooltip: {},
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.deshboard {
  height: 100vh;
  .visited {
    height: 500px;
    width: 600px;
  }
  .card_one {
    padding: 10px;
    .card_baseinfo {
      display: flex;
      border-bottom: 2px solid #ccc;
      padding-bottom: 20px;
      align-items: center;
      img {
        height: 120px;
        width: 120px;
        border-radius: 100%;
      }
      span {
        margin-left: 50px;
      }
      p {
        margin: 0;
        padding: 0;
      }
    }
    .card_detatilinfo {
      span {
        display: flex;
      }
    }
  }
}
</style>

