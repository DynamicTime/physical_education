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

    <div id="addTemplate" class="allTemplate" v-touch:right="eventFun">
      <div v-for="(item ,i) in templateList ">
        <div v-if="templateList[i] =='0'">
          <img @click="spliceList(i)" :src="cross" alt />
          <div @click="showUser()">
            <user class="publicAll user"></user>
          </div>
        </div>
        <div v-if="templateList[i] =='1'">
          <img @click="spliceList(i)" :src="cross" alt />

          <infoShow class="publicAll infoShow"></infoShow>
        </div>

        <div v-if="templateList[i] =='2'">
          <img @click="spliceList(i)" :src="cross" alt />

          <numberIndex class="publicAll numberIndex"></numberIndex>
        </div>
      </div>
    </div>
    <siteUser :siteUserShowP="siteUserShow" @listenUserToMakeForm="listenUser" ></siteUser>
    <!-- 弹出层 -->
    <van-popup v-model="showPopup" position="left" :style="{ height: '100%' }">
      <!-- 左侧弹出框 -->
      <div id="sidebar">
        <sidebar @listenToMakeForm="listenToMakeForm"></sidebar>
      </div>
    </van-popup>
  </div>
</template>
<style scoped>
img {
  width: 25px;
  height: 25px;
  /* float: right; */
  /* margin: 20px; */
  position: absolute;
  left: 300px;
}
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

.allTemplate {
  height: 550px;
  border: 2px solid #fecd2a;
  margin: 30px;
  background-color: #fff;
}
.publicAll {
  background-color: #fff;
  border: 0 solid #e0e9ea;
  margin-top: 10px;
  margin-left: auto;
  margin-right: auto;
}

>>> .body {
  border: 0;
  margin: 0;
}
.user {
  /* width: 85%; */
}
.infoShow {
  /* width: 80%; */
}
.numberIndex {
  /* width: 80%; */
}
</style>
<script>
import sidebar from "../../../components/Super/template/sidebar";
import user from "../../../components/Super/library/user";
import infoShow from "../../../components/Super/library/infoShow";
import numberIndex from "../../../components/Super/library/numberIndex";

import siteUser from "../../../components/Super/template/siteUser";
// import siteUser from "../../../components/Super/template/siteUser";
// import siteUser from "../../../components/Super/template/siteUser";

export default {
  components: {
    sidebar,
    user,
    infoShow,
    numberIndex,
    siteUser
  },
  data() {
    return {
      showPopup: false, // 遮罩层弹出
      templateList: [0],

      allTemplate: ["<user class=&quot;publicAll user&quot;></user>"],
      cross: require("../../../assets/super/template/cross.png"),

      siteUserShow: false ,// 显示user设置底部弹框
    };
  },
  mounted() {
    // this.addTemplate();
    this.start();
  },

  methods: {

    // 接收子组件底部弹框数据
    listenUser(newVal,isTrueList) {
      this.siteUserShow = newVal;
      console.log(isTrueList)
    },

    // 点击user内容弹出底部弹框
    showUser() {
      this.siteUserShow = true;
    },
    // 初始化内容
    start() {
      this.showPopup = false;
      this.siteUserShow= false;
    },
    // 返回按钮
    returnPage() {
      window.history.go(-1); // windos的返回上一页
      // this.$router.go(-1) // vue的返回上一页
    },

    //下一步按钮
    nextStep() {
      this.$router.push({ name: "makeForm" });
    },

    // 子组件sidebar返回事件，返回是哪个组件
    listenToMakeForm(newVal1) {
      this.showPopup = false;
      this.templateList.push(newVal1); // 添加一个组件

      // this.addTemplate();
    },

    // 删除第i个组件
    spliceList(i) {
      this.templateList.splice(i, 1);
    },

    // 右划事件
    eventFun() {
      this.showPopup = true; // 侧边栏左侧显示

      // var t = document.getElementById("sidebar");
      // t.style.cssText = "display:inline";
    },

    // 添加内容方法
    addTemplate() {
      var ff = document.getElementById("addTemplate");

      // ff.innerHTML = "<user ></user>";

      // ff.innerHTML="<p>I love <em>JavaScript</em>!</p>";
    }
  }
};
</script>
