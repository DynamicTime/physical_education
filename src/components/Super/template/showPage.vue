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

    
  </div>
</template>
<style scoped>
.body {
  height: 550px;
  border: 2px solid #fecd2a;
  margin: 10px;
  margin-top: 30px;
}
</style>
<script>
export default {
  data() {
    return {
      show: false,
      value: "",
      infoShow: require("../../assets/super/library/infoShow.jpg"),
      Loop:""  // 定时器
      // infoShow:require("../../assets/super/libraryinfoShow.jpg")
    };
  },
  mounted() {},
  methods: {
    touchin() {
      clearInterval(this.Loop); //再次清空定时器，防止重复注册定时器
      this.Loop = setTimeout(
        function() {
          // alert("是否确认删除");
        }.bind(this),
        1000
      );
    },
    cleartime() {
      // 这个方法主要是用来将每次手指移出之后将计时器清零
      clearInterval(this.Loop);
    },


    
  }
};
</script>
