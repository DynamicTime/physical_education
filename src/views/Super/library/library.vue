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

    <vuedraggable v-model="list" :options="options">
      <div class="bodyDiv" v-for="(item ,index) in list ">
        <!-- 下拉框所有内容 -->
        <van-collapse class="publicClassification" v-model="list[index].activeNames" accordion>
          <van-collapse-item v-if="list" :title="list[index].title" name="1">
            <!-- 左滑显示添加删除等 -->
            <van-swipe-cell>

              <!-- 不同下拉框里面不同内容 -->
              <user v-if="list[index].num == '0'"></user>
              <infoShow v-if="list[index].num == '1'"></infoShow>
              <numberIndex v-if="list[index].num =='2'"></numberIndex>
              <user v-if="list[index].num == '3'"></user>
              <user v-if="list[index].num == '3'"></user>

              

              <!-- 左滑显示的内容 -->
              <template #right>
                <van-button @click="useComponent(index)" v-if="list[index].num !='3'" square text="使用" type="primary" class="delete-button" />
                <van-button v-if="list[index].num =='3'" @click="disableComponent()" square text="停用" type="danger" class="delete-button" />
              </template>
            </van-swipe-cell>
          </van-collapse-item> 
        </van-collapse>
      </div>
    </vuedraggable>
  </div>
</template>
<style scoped>
.goods-card {
  margin: 0;
  background-color: @white;
}

.delete-button {
  height: 100%;
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

import vuedraggable from "vuedraggable"; //拖动

import swipeCell from "../../../components/Super/template/swipeCell"; // 左右滑动

export default {
  components: {
    user,
    infoShow,
    numberIndex,
    vuedraggable,
    swipeCell
  },
  data() {
    return {
      list: [
        { activeNames: "1", title: "用户信息组件", num: "0" },
        { activeNames: "1", title: "信息显示组件", num: "1" },
        { activeNames: "1", title: "数组输入组件", num: "2" },
        { activeNames: "1", title: "无效组件", num: "3" }
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
    // 抬头左侧点击模板管理跳转
    intoManagement() {
      this.$router.push({ name: "management" });
    },

    // 组件右划使用按钮操作
    useComponent(index){
      console.log(index)
    },

    // 组件右划停用按钮操作
    disableComponent(){

    }
  }
};
</script>
