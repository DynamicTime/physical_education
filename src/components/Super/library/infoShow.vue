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
    <div class="body">
      <div class="info1"  v-for="(item, index) in infoTitle">
        <div class="showTitle1">{{infoTitle[index]}}</div>
        <div v-if="infoShow" class="showInfo1">{{infoShow[index]}}</div>
      </div>
      <!-- <div class="info2">
        <div class="showTitle2"></div>
        <div class="showInfo2"></div>
      </div>
      <div class="info3">
        <div class="showTitle3"></div>
        <div class="showInfo3"></div>
      </div>-->
    </div>
  </div>
</template>
<style scoped>
.body {
  width: 278px;
  height: 98px;
  /* background-color: red; */
  border: 1px solid ;
}

div .info1 {
  overflow: hidden;
  width: 68px;
  height: 78px;
  margin: 10px;
  float: left;
  /* background-color: yellow; */
  border: 1px solid white;
  position: relative;
  font-size: 14px;
  color: black;
}
.info1 .showTitle1 {
  width: 58px;
  height: 28px;
  /* background-color: black; */
  border: 1px solid white;
  position: absolute;
  top: 5px;
  left: 4px;
}

.info1 .showInfo1 {
  width: 58px;
  height: 28px;
  /* border: 1px solid white; */
  background-color: white;
  position: absolute;
  /* top:165; */
  bottom: 5px;
  left: 4px;
}
</style>
<script>
export default {
  data() {
    return {
      show: false,
      value: "",
      infoTitle: ["某某得分", "某某信息", "评分"],
      infoShow:["122","122","333"]

    };
  },
  mounted() {},
  methods: {
    // newitems() {
    //   var searchArr = [];
    //   if (this.searchMessage === "") {
    //   }
    // }
  }
};
</script>
