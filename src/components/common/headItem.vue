<template>
  <div class="head_container">
    <div class="head_title">
      <span class="system">后台管理系统</span>
      <div class="rightstyle">
        <div class="btn-fullscreen" @click="handleFullScreen">
          <el-tooltip :content="fullscreen ? '取消全屏' : '全屏'" placement="bottom">
            <i class="el-icon-rank"></i>
          </el-tooltip>
        </div>
        <div class="message">
          <el-tooltip content="有两条未读消息" placement="bottom">
            <i class="el-icon-bell"></i>
          </el-tooltip>
        </div>
        <div class="backpic">
          <img class="bcpic" src="../../assets/img/img.jpg" alt>
        </div>
        <div>
          <el-dropdown>
            <span class="el-dropdown-link" trigger="click">
              <div class="admin">
                <p>admin</p>
                <i class="el-icon-arrow-down el-icon--right"></i>
              </div>
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>关于作者</el-dropdown-item>
              <el-dropdown-item>项目仓库</el-dropdown-item>
              <el-dropdown-item>推出登录</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fullscreen: false
    };
  },
  methods: {
    handleFullScreen() {
      let element = document.documentElement;
      if (this.fullscreen) {
        if (document.exitFullscreen) {
          document.exitFullscreen();
        } else if (document.webkitCancelFullScreen) {
          document.webkitCancelFullScreen();
        }
      } else {
        if (element.requestFullscreen) {
          element.requestFullscreen();
        } else if (element.webkitRequestFullScreen) {
          element.webkitRequestFullScreen();
        }
      }
      this.fullscreen = !this.fullscreen;
    }
  }
};
</script>

<style lang='scss'>
.head_container {
  display: block;
  position: absolute;
  left: 0;
  top: 0px;
  height: 70px;
  width: 100%;
  font-size: 22px;
  color: #fff;
  background-color: #40454e;
  .head_title {
    display: flex;

    align-items: center;
    height: 100%;
    .system {
      padding-left: 100px;
    }
    .rightstyle {
      display: flex;
      position: fixed;
      right: 40px;

      .btn-fullscreen {
        display: flex;

        align-items: center;

        transform: rotate(45deg);
        padding: 8px;
      }
      .message {
        display: flex;
        padding: 8px;
        align-items: center;
      }
      .backpic {
        display: flex;
        padding: 10px;
        align-items: center;
        .bcpic {
          width: 40px;
          height: 40px;
          border-radius: 50%;
        }
      }
      .admin {
        color: #fff;
        display: flex;
        padding: 10px;
        align-items: center;
      }
    }
  }
}
</style>
