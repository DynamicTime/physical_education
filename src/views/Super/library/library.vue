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
      <div class="button"  @click="intoModel()">模板管理</div>
      <div class="titleName">组件管理</div>
    </div>

    <div class="bodyDiv">
      <van-collapse class="publicClassification" v-model="activeNames1">
        <van-collapse-item class="collapseOne" :title="title1" name="1">
          <user></user>
        </van-collapse-item>
      </van-collapse>

      <van-collapse class="publicClassification" v-model="activeNames2">
        <van-collapse-item class="collapseOne" :title="title2" name="1">
          <infoShow></infoShow>
        </van-collapse-item>
      </van-collapse>

      <van-collapse class="publicClassification" v-model="activeNames3">
        <van-collapse-item class="collapseOne" :title="title3" name="1">
          <numberIndex></numberIndex>
        </van-collapse-item>
      </van-collapse>
    </div>
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

.publicClassification{
  margin-top: 20px;
}
</style>


<script>
import user from "../../../components/Super/library/user";
import infoShow from "../../../components/Super/library/infoShow";
import numberIndex from "../../../components/Super/library/numberIndex";

numberIndex
export default {
  components: {
    user,
    infoShow,
    numberIndex
  },
  data() {
    return {
      // show: false,
      // value: ""
      activeNames1: ["1"],
      activeNames2: ["1"],
      activeNames3: ["1"],

      title1: "用户信息组件",
      title2: "信息显示组件",

      title3: "数组输入组件"

    };
  },
  mounted() {},
  methods: {
    // newitems() {
    //   var searchArr = [];
    //   if (this.searchMessage === "") {
    //   }
    // }
    intoModel(){

      
    }
  }
};
</script>
