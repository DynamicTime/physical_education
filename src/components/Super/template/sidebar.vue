<!--
*@描述:侧边栏
*@版本:V1.0
*@作者:白爱民
*@Date:2019年12月11日20:16:26
*@最后修改人:herry
*@LastEditTime:2019年12月11日20:16:31
*@说明：-->
<template>
  <div>
    <div class="leftBody">
      <div class="titleName">组件库</div>
      <div class="librarys">
        <user class="user"></user>
      </div>
    </div>
  </div>
</template>
<style scoped>
.leftBody {
  width: 200px;
  height: 600px;
  border: 1px solid black;
  margin: 30px 10px 10px 10px;
  position: relative;
  z-index: 2;
}
.titleName {
  float: left;
  font-size: 25px;

}

.librarys {
  width: 30px;
  height: 30px;
  position: absolute;

}
.user {
  width: 30px;
  height: 30px;
}
</style>

<script>
import user from "../library/user";
import infoShow from "../library/infoShow";
import numberIndex from "../library/numberIndex";
export default {
  components: {
    user,
    infoShow,
    numberIndex
  },
  data() {
    return {
      show: false,
      value: ""
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
