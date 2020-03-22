<!--
*@描述:组件库
*@版本:V1.0
*@作者:白爱民
*@Date:2020年3月17日11:11:28
*@最后修改人:白爱民
*@LastEditTime:2020年3月17日11:11:34
*@说明：-->
<template>
  <div>
    <div class="title commonColor">
      <div class="button" @click="intoModel()">模板管理</div>
      <div class="titleName">组件管理</div>
    </div>

    <vuedraggable v-model="list" :options="options">
      <div class="bodyDiv" v-for="(item ,index) in list ">
        <van-collapse class="publicClassification" v-model="list[index].activeNames" accordion>
          <van-collapse-item v-if="list" class="collapseOne" :title="list[index].title" name="1">
            <user v-if="list[index].num == '0'"></user>

            <infoShow v-if="list[index].num == '1'"></infoShow>

            <numberIndex v-if="list[index].num =='2'"></numberIndex>
          </van-collapse-item>
        </van-collapse>
      </div>
    </vuedraggable>
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

.bodyDiv {
  margin-top: 50px;
  /* width: 80%; */
  /* margin: 10px auto 10px; */
  margin-left: 15px;
  margin-right: 15px;
}

>>> .van-cell {
  /* height: 100px; */
  text-align: left;
  font-size: 20px;
}

.publicClassification {
  margin-top: 20px;
}
</style>


<script>
import user from "../../../components/Super/library/user";
import infoShow from "../../../components/Super/library/infoShow";
import numberIndex from "../../../components/Super/library/numberIndex";

import vuedraggable from "vuedraggable";  //拖动

export default {
  components: {
    user,
    infoShow,
    numberIndex,
    vuedraggable
  },
  data() {
    return {
      

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
      }

    };
  },
  updated() {
    // console.log(this.list);
  },
  mounted() {},
  methods: {

    intoModel() {
      this.$router.push({name:"management"});
    }

  }
};
</script>
