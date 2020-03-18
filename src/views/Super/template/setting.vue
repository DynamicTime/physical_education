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
      <div class="button" @click="intoModel()">模板管理</div>
      <div class="titleName">模板设置</div>
    </div>

    <div class="body">
      <div class="nameTitle">分组设置</div>
      <div class="nameNum">
        <div class="project" v-for="(item,index) in projectName">
          <div class="projectName">{{projectName[index]}}</div>
          <!-- <div class="projectBut"> -->
          <img class="projectBut" :src="less" alt />
          <!-- </div> -->
        </div>
      </div>
      <div>
        <img class="addBut" :src="plus" alt />
      </div>
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

.body {
  margin: 20px auto 20px;
  width: 335px;
  height: 500px;
  border: 1px solid red;
}

.nameTitle {
  border: 1px solid #e0e9ea;
  float: left;
  margin: 10px;
}

.nameNum {
  border: 1px solid #e0e9ea;
  width: 300px;
  /* height: 300px; */
  margin: 50px auto 20px;
}

.project {
  width: 300px;
  height: 40px;
  border: 1px solid #fecd2a;
  background-color: #fecd2a;
  margin-top: 20px;
}

.projectName {
  float: left;
  /* text-align: center; */
  margin: 3%;
}

.projectBut {
  width: 40px;
  height: 40px;
  float: right;
}

.addBut {
  height: 40px;
  width: 40px;
  margin: 10px auto;
}
</style>
<script>
export default {
  data() {
    return {
      //   show: false,
      //   value: ""

      less: require("../../../assets/super/Less.png"),
      projectName: ["公共项目", "男生项目", "女生项目"],
      plus: require("../../../assets/super/plus.png")
    };
  },
  mounted() {},
  methods: {
    // newitems() {
    //   var searchArr = [];
    //   if (this.searchMessage === "") {
    //   }
    // }

    intoModel() {
      this.$router.push({ name: "management" });
    }
  }
};
</script>
