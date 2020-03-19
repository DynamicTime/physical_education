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
      <!-- <div class="iocNameDiv"> -->
        <img @click="intoSetting" class="iocName" :src="iocName" alt />
      <!-- </div> -->

      <div class="button" @click="intoModel()">组件管理</div>
      <div class="titleName">模板管理</div>
      <!-- <div class="iocName"> -->
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

.title .iocName {
  /* background: none; */
  float: right;
  /* position: fixed; */
  width: 50px;
  height: 50px;
  /* left: 350px; */
}

</style>
<script>
export default {
  data() {
    return {
      //   show: false,
      //   value: ""
      iocName: require("../../../assets/super/setting.png")
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
      this.$router.push({ name: "library" });
    },
    intoSetting() {
      this.$router.push({ name: "setting" });
    }
  }
};
</script>
