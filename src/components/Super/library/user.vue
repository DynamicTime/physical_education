<!--
*@描述:用户信息组件
*@版本:V1.0
*@作者:白爱民
*@Date:2019年12月11日20:16:26
*@最后修改人:herry
*@LastEditTime:2019年12月11日20:16:31
*@说明：-->
<template>
  <div>
    <div class="body">
      <div class="picture">
        <img :src="picInfo" alt />
      </div>

      <div class="rightData">
        <div class="info" v-for="(item ,i) in infoName" v-if="nameIsTrue[i]">
          <div class="infoName">{{infoName[i].name}}</div>
          <div class="infoData">{{infoName[i].data}}</div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.body {
  width: 298px;
  height: 190px;
  border: 1px solid;
  position: relative;
}
.picture img {
  width: 100px;
  height: 120px;
  margin: 30px auto;
}
.body .picture {
  width: 100px;
  height: 140px;
  top: 4px;
  bottom: 4px;
  border: 1px solid white;
  position: absolute;
}

/* 左边大边框 */
.body .rightData {
  width: 176px;
  height: 190px;
  position: absolute;
  left: 120px;
  border: 1px solid white;
  font-size: 15px;
  text-align: left;
  color: black;



    /* line-height:190px; */
  /* text-align: center; */

}
/* 每行数据边框 */
.body .info {
  border: 1px solid white;
 /* display:inline-block; */
}

/* 每行数据左边的属性边框 */
.infoName {
  margin-right: 20px;
  display: inline-block;
  border: 1px solid white;
}
/* 每行数据左边的数据边框 */
.infoData {
  display: inline-block;
  border: 1px solid white;
}
</style>
<script>
export default {
  data() {
    return {
      infoName: [
        { name: "名字", data: "白爱民" },
        { name: "性别", data: "男" },
        { name: "学号", data: "122231231231" },
        { name: "学院", data: "建工学院" },
        { name: "专业", data: "电子信息" },
        { name: "班级", data: "二班" },
        { name: "年级", data: "一年级" }
      ],
      picInfo: require("../../../assets/super/user.png"),

      nameIsTrue: [false, true, true, true, true, true, true]
    };
  },
  mounted() {},
  methods: {}
};
</script>
