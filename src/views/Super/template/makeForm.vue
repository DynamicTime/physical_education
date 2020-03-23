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
      <!-- <user class="publicAll user"></user> -->

      <!-- <infoShow class="publicAll infoShow"></infoShow> -->

      <!-- <numberIndex class="publicAll numberIndex"></numberIndex> -->
    </div>

    <!-- 遮罩层 -->
    <van-popup v-model="showPopup" position="left" :style="{ height: '100%' }">
      <!-- 左侧弹出框 -->
      <div id="sidebar">
        <sidebar @listenToMakeForm="listenToMakeForm"></sidebar>
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

export default {
  components: {
    sidebar,
    user,
    infoShow,
    numberIndex
  },
  data() {
    return {
      showPopup: false, // 遮罩层弹出

      list: [
        { activeNames: "1", title: "用户信息组件", num: "0" },
        { activeNames: "1", title: "信息显示组件", num: "1" },
        { activeNames: "1", title: "数组输入组件", num: "2" }
      ],
      options: {
        delayOnTouchOnly: true, //开启触摸延时
        direction: "vertical", //拖动方向
        delay: 500, //延时时长
        touchStartThreshold: 3, //防止某些手机过于敏感(3~5 效果最好)
        chosenClass: "chosen" //选中之后拖拽项添加的class名(用于选中时候添加样式)
      },

      allTemplate: ["<user class=&quot;publicAll user&quot;></user>"]
    };
  },
  mounted() {
    // this.addTemplate();
  },
  methods: {
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
      // console.log(newVal1);
      this.addTemplate();
    },

    // 右划事件
    eventFun() {
      this.showPopup = true; // 侧边栏左侧显示

      // var t = document.getElementById("sidebar");
      // t.style.cssText = "display:inline";
    },

    addTemplate() {
      var ff = document.getElementById("addTemplate");

      ff.innerHTML = "<user ></user>";
      // ff.innerHTML="<p>I love <em>JavaScript</em>!</p>";
    }
  }
};
</script>
