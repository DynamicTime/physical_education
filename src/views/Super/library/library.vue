<!--
*@描述:组件库
*@版本:V1.0
*@作者:白爱民
*@Date:2020年3月17日11:11:28
*@最后修改人:白爱民
*@LastEditTime:2020年3月17日11:11:34
*@说明： 让每个类型组件抽成一个，然后在这个页面可以跳转顺序，停用使用在各自的里面使用、

-->
<template>
  <div>
    <div class="title commonColor">
      <div class="button" @click="intoManagement()">模板管理</div>
      <div class="titleName">组件管理</div>
    </div>

    <!-- 可以长按拖动内容 -->
    <vuedraggable v-model="classList" :options="options">
      <div class="bodyDiv" v-for="(item ,index) in classList">
        <userInfo
          :titleP="classList[index].title"
          v-if="classList[index].isTrue && classList[index].position == 0"
        ></userInfo>
        <theMessageStates
          :titleP="classList[index].title"
          v-if="classList[index].isTrue && classList[index].position == 1 "
        ></theMessageStates>
        <enterInformation
          :titleP="classList[index].title"
          v-if="classList[index].isTrue && classList[index].position == 2"
        ></enterInformation>
      </div>
    </vuedraggable>
  </div>
</template>
<style scoped>
/* ===============抬头部分================= */

.title {
  overflow: hidden;
  border: 1px solid #fecd2a;
  width: auto;
  height: 48px;
  /* background: #FECD2A; */
}
.button {
  float: left;
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

.commonColor {
  background: #fecd2a;
}
/* ===============抬头部分================= */

.bodyDiv {
  margin-top: 50px;
  margin-left: 15px;
  margin-right: 15px;
}

/* 每个模板名字居左 */
>>> .van-cell {
  text-align: left;
  font-size: 20px;
}
</style>


<script>
import userInfo from "../../../components/Super/library/userInfo/userInfo";
import theMessageStates from "../../../components/Super/library/theMessageStates/theMessageStates";
import enterInformation from "../../../components/Super/library/enterInformation/enterInformation";
import vuedraggable from "vuedraggable"; //拖动

import swipeCell from "../../../components/Super/template/swipeCell"; // 左右滑动

export default {
  components: {
    userInfo,
    theMessageStates,
    enterInformation,
    vuedraggable,
    swipeCell
  },
  data() {
    return {
      classList: [
        { title: "用户信息组件", isTrue: true, position: 0 },
        { title: "信息显示组件", isTrue: true, position: 1 },
        { title: "数组输入组件", isTrue: true, position: 2 },
        { title: "无效组件", isTrue: true, position: 3 }
      ],
      options: {
        delayOnTouchOnly: true, //开启触摸延时
        direction: "vertical", //拖动方向
        delay: 500, //延时时长
        touchStartThreshold: 3, //防止某些手机过于敏感(3~5 效果最好)
        chosenClass: "chosen" //选中之后拖拽项添加的class名(用于选中时候添加样式)
      }
    };
  },
  updated() {},
  mounted() {
    // this.start();
  },
  methods: {
    start() {},
    // 抬头左侧点击模板管理跳转
    intoManagement() {
      this.$router.push({ name: "management" });
    }
  }
};
</script>
