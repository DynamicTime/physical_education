<!--
*@描述:test
*@版本:V1.0
*@作者:白爱民
*@Date:2019年12月11日20:16:26
*@最后修改人:herry
*@LastEditTime:2019年12月11日20:16:31
*@说明：-->
<template>
  <div>
    <div class="title commonColor">
      <div class="buttonLeft" @click="returnPage()">返回</div>
      <div class="buttonRight" @click="nextStep()">下一步</div>
      <div class="titleName">编辑模板</div>
    </div>
    <div class="body" v-touch:right="eventFun"></div>

    <!-- 遮罩层 -->
    <van-popup v-model="showPopup" position="left" :style="{ height: '100%' }">
      <!-- 左侧弹出框 -->
      <div id="sidebar" >
        <sidebar></sidebar>
      </div>
    </van-popup>
  </div>
</template>
<style scoped>
.commonColor {
  background: #fecd2a;
}

.title {
  overflow: hidden;
  border: 1px solid #fecd2a;
  width: auto;
  height: 48px;
  /* background: #FECD2A; */
}
.buttonLeft {
  float: left;
  width: 100px;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-bottom: auto;
  font-size: 20px;
}
.buttonRight {
  float: right;
  width: 100px;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-bottom: auto;
  font-size: 20px;
}
.titleName {
  margin: 10px auto 10px;
  font-size: 20px;
  width: 100px;
}

.body {
  height: 550px;
  border: 2px solid black;
  margin: 10px;
  margin-top: 30px;
}
</style>
<script>
import sidebar from "../../../components/Super/template/sidebar";
export default {
  components: {
    sidebar,
  },
  data() {
    return {
      // show: false,
      // value: "",
      showPopup: false  // 遮罩层弹出
    };
  },
  mounted() {},
  methods: {
    // 返回
    returnPage() {
      window.history.go(-1); // windos的返回上一页
      // this.$router.go(-1) // vue的返回上一页
    },

    //下一步
    nextStep() {
      // console.log("2");
      this.$router.push({ name: "makeForm" });
    },

    eventFun() {
      console.log("右划");
      this.showPopup = true;
      // this.sidebarShow=true

      // var t = document.getElementById("sidebar");
      // t.style.cssText = "display:inline";
    }
  }
};
</script>
