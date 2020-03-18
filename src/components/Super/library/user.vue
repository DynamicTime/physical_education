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
      <div class="picture">
        <img :src="picInfo" alt />
      </div>
      <div class="name">{{name}}</div>
      <div class="info">
        <!-- 学号：12312312
        年级：12围墙43123
        学校：2 -->
      </div>
    </div>
  </div>
</template>
<style scoped>
.body {
  width: 298px;
  height: 148px;

  /* background-color: red; */
  border: 1px solid;
  position: relative;
}
.picture img {
  width: 100px;
  height: 100px;
  margin-top: 20px;
}
.body .picture {
  width: 100px;
  height: 140px;
  /* margin-top: 4px; */
  top: 4px;
  bottom: 4px;
  /* background-color: yellow; */
  border: 1px solid white;
  position: absolute;

  /* background-image: url(); */

  /* background: url(/user.png); */
}

.body .name {
  /* background-color: blue; */
  width: 100px;
  height: 20px;
  float: left;
  position: absolute;
  left: 120px;
  /* top: 5px; */
  border: 1px solid white;
  font-size: 20px;
  text-align: left;
  color: black;
}
.body .info {
  background-color: yellow;
  width: 160px;
  height: 100px;
  float: left;
  position: absolute;
  margin-left: 120px;
  margin-top: 40px;
}
</style>
<script>
export default {
  data() {
    return {
      name:"herry",
      picInfo:require("../../../assets/super/user.png")
    };
  },
  mounted() {},
  methods: {}
};
</script>
